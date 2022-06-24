<img align="right" src="https://github.com/braingu/tadpole/blob/master/images/TLP/TLPAmber.png">

Many troubleshooting engagements involve SSL/TLS issues. Sometimes it’s “this service isn’t working” or “they can’t talk to each other” or “here’s this error”. No matter what the error message is, the keys to resolution are

*   understanding the foundational concepts around PKI,
*   applying OpenSSL magic, and then
*   carefully reading the results to find the root of the problem.

# PKI

It’s important to have a solid, foundational understanding of the underlying concepts of PKI before you can begin to troubleshoot errors.

## Resources for understanding PKI

*   [https://www.securew2.com/blog/public-key-infrastructure-explained/](https://www.securew2.com/blog/public-key-infrastructure-explained/) (9/2019)
*   [https://www.altaro.com/hyper-v/public-key-infrastructure/](https://www.altaro.com/hyper-v/public-key-infrastructure/) (11/2018) Corporate, but good stuff provided you can ignore the hyper-v promos
*   [https://keychest.net/stories/understanding-pki-for-busy-folks](https://keychest.net/stories/understanding-pki-for-busy-folks) (March 2020)
*   [https://pki-tutorial.readthedocs.io/en/latest/](https://pki-tutorial.readthedocs.io/en/latest/) (no date but OpenSSL-specific)
*   [https://www.giac.org/paper/gsec/2171/idiots-guide-public-key-infrastructure/103692](https://www.giac.org/paper/gsec/2171/idiots-guide-public-key-infrastructure/103692) (9/2002) Note:  This is a good paper, but needs to be updated to do things like replace MD5 with SHA2.
*   [https://www.techrepublic.com/article/a-beginners-guide-to-public-key-infrastructure/](https://www.techrepublic.com/article/a-beginners-guide-to-public-key-infrastructure/) (9/2005)
*   [Cryptography For Dummies - Page 97 - Google Books Result](https://books.google.com/books?id=b3pQDh7j5ogC&pg=PA97&lpg=PA97&dq=PKI+for+dummies&source=bl&ots=uatmc2AA-d&sig=ACfU3U1FNgzNM-DPuRD-Z9s9EgL8bn_fRg&hl=en&sa=X&ved=2ahUKEwjlpbzTkZvpAhVDgnIEHTPOC6MQ6AEwGHoECBQQAQ) (2004)


# SSL/TLS Errors

[https://maulwuff.de/research/ssl-debugging.html](https://maulwuff.de/research/ssl-debugging.html)

When you get an error, google it to figure out the error, although some are cryptic. Some involve lower level handshake stuff.

Some OpenSSL magic can bring those things to the surface pretty quickly


# OpenSSL

*   [https://www.feistyduck.com/books/openssl-cookbook/](https://www.feistyduck.com/books/openssl-cookbook/)
*   [https://www.sslshopper.com/article-most-common-openssl-commands.html](https://www.sslshopper.com/article-most-common-openssl-commands.html)


# Reading the logs

*   **Error messages**. Read the whole error, not just the bit that interests you. Sometimes the logging is too verbose, or there’s a false indicator as to the problem, and people tend to not read the whole error message, or not go back far enough to look at what initiated the failure.
*   **Scroll back**. Say you’re tailing a log file, or log output through a web interface. You have to actively scroll back.
*   Printing cert info
*   **Match certs to keys**.
Usually at least two points to a log or a stack trace
    *   **Where it happens** -- not properly identifying which bit is important in the stack. This can be challenging. Maybe knowing your language, and how it dumps those traces out, is key here.
    *   **What happened** -- your error message. The quality of the error message is dependent on who wrote the message. More polished code has better error messages.

    If the “what” isn’t super clear, you can fall back on the “where.” So if the error makes no sense, figure out which line in which file in the codebase it happened. Reverse what’s going on, figure out the logic path that got me there, and then figure out how to work around, fix, or patch, and then go from there.

*   **s_client**


## s_client

*   [https://support.pingidentity.com/s/article/OpenSSL-s-client-Commands](https://support.pingidentity.com/s/article/OpenSSL-s-client-Commands)
*   [https://linux.die.net/man/1/s_client](https://linux.die.net/man/1/s_client)
*   [https://www.openssl.org/docs/man1.0.2/man1/s_client.html](https://www.openssl.org/docs/man1.0.2/man1/s_client.html)
*   [https://security.stackexchange.com/questions/70733/how-do-i-use-openssl-s-client-to-test-for-absence-of-sslv3-support](https://security.stackexchange.com/questions/70733/how-do-i-use-openssl-s-client-to-test-for-absence-of-sslv3-support)
*   [https://www.feistyduck.com/library/openssl-cookbook/online/ch-testing-with-openssl.html](https://www.feistyduck.com/library/openssl-cookbook/online/ch-testing-with-openssl.html)


### Using s_client

1. Connect to a server

  `openssl s_client -connect server.example.com:443`

 This will indicate if the TLS connection is functional. You made a request; if things are happy path, you will get a response containing the server’s public certs, and debug info about the TLS session itself.


2. Connect to a server and specify a CA

  `openssl s_client -connect server.example.com:443 -CAfile /path/to/myca.crt`

 Does the same as 1, but allows you to specify a CA file outside of your system’s store. This is useful for testing connections to systems with self-signed certs.

3. Extract the remote certificates

  `openssl s_client -showcerts -verify 5 -connect amazon.com:443`

  Will enumerate the certificate and verify five layers deep.  Our above example should print out something like

  ![extract the remote certificate](images/pki1.png)

   which gives us the subject of each cert in the chain and the depth. It will also spit out the contents of the chain. The certs at depth 1 and above could be added to a trust store if they are self-signed.

   ![certificate chain](images/pki2.png)

   A one-liner to spit out and save all of the certs in a response to a file named using their subject would be:

   `openssl s_client -showcerts -verify 5 -connect amazon.com:443 &lt; /dev/null | awk '/BEGIN/,/END/{ if(/BEGIN/){a++}; out="cert"a".crt"; print >out}' && for cert in *.crt; do newname=$(openssl x509 -noout -subject -in $cert | sed -n 's/^.*CN=\(.*\)$/\1/; s/[ ,.*]/_/g; s/__/_/g; s/^_//g;p').pem; mv $cert $newname; done`

  ![alt_text](images/pki3.png)

  **Note:** the `awk` and `regex` magic doing the splitting and renaming isn’t important here.  More on this topic later.


4. Connect using a client key-pair

  `openssl s_client -connect example.com:443 -cert cert.pem -key key.pem -state -debug`

  The state and debug flags will add some useful debug statements such as

  ```
  SSL_connect:SSLv3 read server done A
  SSL_connect:SSLv3 write client certificate A
  ```

5. Test other protocols (smtp, pop3, imap, ftp, and xmpp)

  `openssl s_client -connect pop.gmail.com:993 -starttls pop3`



## Reading the logs

*   **Error messages**. Read the whole error, not just the bit that interests you. Sometimes the logging is too verbose, or there’s a false indicator as to the problem, and people tend to not read the whole error message, or not go back far enough to look at what initiated the failure.
*   **Scroll back**. Say you’re tailing a log file, or log output through a web interface. You have to actively scroll back.
*   Printing cert info
*   Matching certs to keys

*   Usually at least two points to a log or a stack trace:
    *   Where it happens -- not properly identifying which bit is important in the stack. This can be challenging. Maybe knowing your language, and how it dumps those traces out, is key here.
    *   What happened -- your error message. Dependent on who wrote the message. More polished code has better error messages.
*   If the “what” isn’t super clear, you can fall back on the where. “That makes no sense but it happened on this line in this file in this codebase. Reverse what’s going on, figure out the logic path that got me there, and then figure out how to work around, fix, or patch, and then go from there.


##  awk magic

Awk is a Linux primitive tool used for searching text and matching patterns. Feed awk input and a set of rules, and it performs actions on that text based on that set of tools. Awk can be used in countless ways: any time you need to quick ‘n dirty search for text, extract text, substitute text. Anything you need to do with text and a pattern.

In the prior example, it’s being used to extract the cert body out of the OpenSSL s_client. It looks for begin and end tags, and extracts the data we care about out of the output based on those tags. Later on, use regex to further pull the subject name out and rename the files. Pulling out the common name, stripping out periods and spaces, and replacing them with underscores. That gives your file a friendly name.

*   [https://www.gnu.org/software/gawk/manual/gawk.html](https://www.gnu.org/software/gawk/manual/gawk.html)
*   [https://www.grymoire.com/Unix/Awk.html](https://www.grymoire.com/Unix/Awk.html)
*   [https://linuxhint.com/20_awk_examples/](https://linuxhint.com/20_awk_examples/)
*   [https://www.tutorialspoint.com/awk/index.htm](https://www.tutorialspoint.com/awk/index.htm)
*   [https://likegeeks.com/awk-command/](https://likegeeks.com/awk-command/)
*   … and if you have a specific concern, SO is always your friend.


## regex magic

This is the pattern for those rules. Truly ubiquitous. Matt Shaver is the regex wizard; direct questions to him.


*   [https://medium.com/factory-mind/regex-cookbook-most-wanted-regex-aa721558c3c1](https://medium.com/factory-mind/regex-cookbook-most-wanted-regex-aa721558c3c1)
*   [https://medium.com/factory-mind/regex-tutorial-a-simple-cheatsheet-by-examples-649dc1c3f285](https://medium.com/factory-mind/regex-tutorial-a-simple-cheatsheet-by-examples-649dc1c3f285)
*   [https://regular-expressions.mobi/index.html?wlr=1](https://regular-expressions.mobi/index.html?wlr=1)
    *   Start here: [https://www.regular-expressions.info/quickstart.html?wlr=1](https://www.regular-expressions.info/quickstart.html?wlr=1)

** Regex testers**

*   [https://regexr.com/](https://regexr.com/)


### Troubleshooting

A lot of people troubleshoot by throwing the kitchen sink at a thing when they’re only solving one problem. Mostly, that backfires and you introduce more problems. You’re throwing yourself onto a different track. Make small, incremental changes that you can revert if your changes don’t solve the issue. A lot of misconfigurations and vulnerabilities are introduced in the name of troubleshooting. Here are some things to be aware of

*   Don’t be afraid to learn new configurations.
*   Expired Certs/CRLs. Be sure to check the “Not valid before, not valid after” dates in the OpenSSL output.
*   Check that the authority you’re trusting is the one authoring the cert.
*   Check for mismatched keys. When people are doing frantic breakfixing they’ll end up with a directory full of crap. They’ll reissue the public key, or mismatch them somehow. Use OpenSSL to find the unique identifier for each, and make sure they match.
*   Check the CA to make sure it’s trusted. If it isn’t, there’s your trouble.


# Resources

*   [https://ma.ttias.be/how-to-read-ssl-certificate-info-from-the-cli/](https://ma.ttias.be/how-to-read-ssl-certificate-info-from-the-cli/)
*   [https://serverfault.com/questions/661978/displaying-a-remote-ssl-certificate-details-using-cli-tools](https://serverfault.com/questions/661978/displaying-a-remote-ssl-certificate-details-using-cli-tools)
*   [https://support.qacafe.com/knowledge-base/how-do-i-display-the-contents-of-a-ssl-certificate/](https://support.qacafe.com/knowledge-base/how-do-i-display-the-contents-of-a-ssl-certificate/)
*   [https://www.digitalocean.com/community/tutorials/java-keytool-essentials-working-with-java-keystores](https://www.digitalocean.com/community/tutorials/java-keytool-essentials-working-with-java-keystores)
