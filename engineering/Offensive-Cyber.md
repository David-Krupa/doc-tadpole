<img align="right" src="https://github.com/braingu/tadpole/blob/master/images/TLP/TLPAmber.png">

Offensive cyber carries a totally different risk profile than defensive cyber.


## Decide who you want to target



*   **Individual**

    If you’re going after random joe individual, you could use whatever. Not really a big deal. No one really cares if you get caught. Shrug it off.

*   **Business**

    If you’re going after a business, it’s more in depth. They have more protections. Firewalls, intrusion prevention/detection, correlating logs, as well as understanding what a business is trying to protect and being aware of that. Be more mindful of what you’re using. Businesses will wipe and reimage rather than dig in. If you can gain info without triggering stuff, it’s a lot easier.

*   **Nation/State**

    Attribution is the biggest thing to worry about. In the event that you’re caught, (tools and techniques get identified), it’s most important that you avoid the attribution aspect. That’s all done in the preparation of the thing — design and testing. Let’s say you’re writing a control system using AWS. When you’re developing it, you don’t use a VPN, and AWS is attributed because you have to pay for it. Then the operation happens, AWS looks through their logs for these characteristics. Then you get tagged. That goes back to the original development and testing of the capabilities. Attribution is the most critical thing, because it has real world consequences. If the tool gets caught, that means you don't use the tool again. Any money effort or time that went into developing it is forfeit.



## Determine the attack surface and strategy (how you want to go about it)


### Vulnerability discovery



*   Fuzzing, directed approaches, static analysis.  \
(See the Library for more information and resources.)
*   A vulnerability causes behaviors that are not expected, so be alert to expected vs. unexpected behavior. For example, if I submit a form on a web page and now the URL is wrong… understanding what a vulnerability or impairment may be is relevant.
*   Not everything has to be drop to kernel > root vulnerability. You can leverage lots of things that give you information.


### Tools



*   Use [!exploitable](https://archive.codeplex.com/?p=msecdbg) — you can feed some applications to it once you tune it, and it’ll tell you if it’s exploitable or not. Otherwise,


### Not-Tools



*   Go through by hand, asking “can I control this? Is it useful?”

    **Example**: Let’s say you spend seven days on discovery phase, and you get 200 crashes. Of those, perhaps five or six could be like memory corruptions you could control, and of those one or two would be exploitable. This is optimistic, but what you’re looking at.



### Crafting the offense



*   Craft your delivery, your payload, and gain code execution. Have that app start executing on their box.
*   Generally, you have to
    *   carve out memory
    *   put your code in
    *   execute your stuff from there
    *   clean up the process memory
    *   let it resume like nothing ever happened.
*   Decide what capabilities you want from
    *   the keylogger
    *   credential harvesting
    *   data mining
    *   antivirus evasion
    *   persistence mechanisms
    *   data exfiltration
*   Manage your C&C
    *   How are you getting information back?
    *   How are you blending in so no one knows what you’re doing?
    *   What are you doing to make sure you’re not flagged?
    *   How do you blend and mask yourself? You can hide processes, but going through a network or firewall, you’re still going to be seen.
