<img align="right" src="https://github.com/braingu/tadpole/blob/master/images/TLP/TLPAmber.png">

# Getting Access to Systems

## P1 SSO
P1 operates environments at IL2, IL4, and IL5.

### If you have a CAC
Go to login.dso.mil and self-register

### If you don't have a CAC
You'll need the following to gain access:
- IL2: Form 2875 signed by a government sponsor
- IL4: Form 2875 signed by a government sponsor, **and** a CAC application in progress
- IL5: N/A - no access is granted without a CAC

Note that you need to submit a separate ticket for each impact level. [This document contains instructions](https://repo1.dso.mil/razor-crest-public/2875s) and an email to submit the form to.

### IL2
Follow the [directions](https://repo1.dso.mil/razor-crest-public/2875s) to fill out your 2875.

Note that you'll need to get the Department symbol for your customer (Box 3) and your BrainGu contract number and contract expiration date (box 16a) - ask your team lead for help finding this.

Complete the Cyber Awareness Challenge linked on the doc above, and make sure the date you put for completing it on your 2875 matches the date on the certificate.

Follow the instructions on the linked doc and then ask your team lead to help get a government sponsor to sign it with their CAC.

### IL4
Follow the instructions for IL2, but also make sure to include "I have a CAC application in progress" in the justification field of your 2875.

### IL5
You'll need a CAC to access IL5. Go to login.dso.mil and register using your account.

## Installing DoD PKI
The Department of Defense uses their own [Root Certificate Authorities](https://en.wikipedia.org/wiki/Root_certificate). These aren't in your computer or browser's trust chain by default, so you'll have to install them before the browser will allow HTTPS connections to sites that use certs under the DoD Root CA.

Follow these instructions to install the DoD Root CA on your machine:
1. Navigate to the DoD Cyber Exchange site: https://public.cyber.mil/pki-pke/tools-configuration-files/#
2. Search for `certificate bundle`
3. Download the `DoD PKI` bundle (e.g. ` PKI CA Certificate Bundles: PKCS#7 for DoD PKI Only - Version 5.9`)
4. (Mac only:) unzip the certificate bundle, open the folder, and double click on `DoD_PKE_PEM.pem`. Your computer will add the certificate file to your Keychain.
- NOTE: This seems to install only DoD Root CA 3, which works for P1 websites as of November 2021. For other DoD sites you may need to trust other Root CAs - you can follow these instructions for the other DoD Root CA files in the bundle you downloaded to trust them as well.
5. (Mac only:) In the Keychain Access app, find the root CA in the list, right-click, and select `Get Info`. You'll see a warning that the root CA is not trusted. Expand the Trust section and set `X.509 Basic Policy` to `Always Trust`.
6. Close the "more info" window. You will be asked for your password.
7. Navigate to a site that uses a cert under the DoD Root CA such as https://login.dso.mil - verify you can load the page. You may not be able to log in, but you should see content on the screen (vs an error from your browser that the site is not secure).

If these instructions don't work for you, post in the `#torch-corp-tech` Slack channel and someone will be glad to help you!
