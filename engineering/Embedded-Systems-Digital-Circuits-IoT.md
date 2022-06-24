<img align="right" src="https://github.com/braingu/tadpole/blob/master/images/TLP/TLPAmber.png">

[“Once you make a light blink, everything else is possible.”](https://en.wikipedia.org/wiki/Blinkenlights)


## Contents
* [Microchips](#microchips)
  * [[Arduino](https://www.arduino.cc/), [Raspberry Pi](https://www.raspberrypi.org/), [GP IO](https://techterms.com/definition/gpio), [Beaglebone](https://learn.adafruit.com/beaglebone)](#arduinohttpswwwarduinocc-raspberry-pihttpswwwraspberrypiorg-gp-iohttpstechtermscomdefinitiongpio-beaglebonehttpslearnadafruitcombeaglebone)
* [Troubleshooting](#troubleshooting)
* [Security / IoT DRM](#security--iot-drm)
  * [Security](#security)
  * [IoT/DRM and Security Research](#iotdrm-and-security-research)
  * [Tools](#tools)
  * [Practice](#practice)



Start with designing things from the ground up. Digital design, microcontrollers.

## Microchips

[PIC18F4520](https://www.microchip.com/wwwproducts/en/en010297), [PIC18F4550](https://www.microchip.com/wwwproducts/en/PIC18F4550) by [Microchip](https://www.microchip.com/).

Like Arduino, but with more scaffolding around them. The 4520 didn't have crystals, so they had to add their own. Most power signals are dirty — they spike and warp, and are often not at the expected value. Micros are super sensitive since they don’t have filter capability themselves. They had the pins, but needed to be programmed for what they were looking for.


### [Arduino](https://www.arduino.cc/), [Raspberry Pi](https://www.raspberrypi.org/), [GP IO](https://techterms.com/definition/gpio), [Beaglebone](https://learn.adafruit.com/beaglebone)

Arduino is good because it has lots of support, lots of capability, various sizes. You can get just Arduino chips (18 mega series), program them, and put them in any system you want; custom devices, services, whatever without big development boards. Also good because it has its own IDE — you can program things, there are tons of libraries, and tons of examples. So even if you’re just blinking lights, it’s super easy. If you want to control relays, motor shields (expandable boards) give you the capability to do other things. Motor to servo to lights, power, relays, anything, there’s a shield that’s almost plug n’ play.

Other platforms (like Beaglebone), you may have to add more to understand.



*   Powerful, lots of support, very extensible, steeper learning curve.
*   It’s imperative that you understand how to read the circuit so you understand what’s going on. The learning curve for understanding everything is very steep. Bypassing that is a key thing. Programming is easy. Microcontrollers either work or they don’t… there’s no debugging in the middle. You have to understand every last thing, and there’s no response unless it works. It’s frustrating and irritating to get into.
*   “Very steep” — so many things you have to pay attention to and get used to. For reference — he wanted to make his own USB device.

    ![](https://github.com/braingu/tadpole/blob/master/images/Arduinomega.jpg)

    ![](https://github.com/braingu/tadpole/blob/master/images/Arduinomega2.jpg)

    ![](https://github.com/braingu/tadpole/blob/master/images/Arduinouno.jpg)

    ![](https://github.com/braingu/tadpole/blob/master/images/Arduinouno2.jpg)

*   Capacitors, pins, chip, crystal — so much to make it work right, from scratch.
*   Arduino — plug a USB cable in and it’s done.
*   Shield you don’t need to config and almost nothing you have to do. Plug in cables, connect to your motor, and line up your pins, and it stick on your Arduino, flash code, and you’re done.
    ![](https://github.com/braingu/tadpole/blob/master/images/ArduinoCNCshield.jpg)
*   Way more work to set up with a build your own, because you also have to build your interfaces.
*   It’s cool to be able to build your own, but not a requirement any more. Unless you’re building custom devices. It’s nice to know they exist, but you don’t have to know a whole lot about the internals.
*   IoT development, not necessary to build your own.
        ![](https://github.com/braingu/tadpole/blob/master/images/Esp32.jpg)


## Troubleshooting

*   If a circuit doesn’t work, start from a known spot, figure out where it stops being known or good…
*   Physical devices are great for building troubleshooting chops. Given an unknown system, how do you fix it?


## Security / IoT DRM


### Security



*   The hard thing to solve there is security enforcement and updates. If you give someone a device, you give them full access whether you mean to or not.
*   Brent makes his own boards — wifi and bluetooth enabled. You can program them to connect through wifi, then interface, and turn the light on and off over wifi. If you’re communicating with it, how do you make sure it’s secure? If your certificate gets compromised, the device is compromised as well. How do you know it is who it says it is?


### IoT/DRM and Security Research



*   From a security perspective, DRM is a great thing. If you have backdoors or different ways of doing things, then everyone else has access to the same things you do. DRM helps you lock things down more effectively, but in the same sense, if you purchase something you should own it completely. Tesla, for instance. If you don’t pay more, you don’t get the upgrades. If you sell the vehicle, there’s no guarantee those things go with the vehicle; they’re assigned to you. If DRM on a TPlink switch, I have more confidence it’s only communicated with that company.
*   Walled garden model kinda works, like for baby monitors. BadPower attack. Devices can override their own safety protection and overheat. Macbook: There is some form of communication with the power supply. Microcontrollers in the machines. If you share a power supply, that could be an avenue to exploit someone. If you compromise the power supply you could cause physical damage.
*   Wireless power outlets have their own wifi/bluetooth access point. You launch their app, they’ll scan for that SSID/bt signature, and if it finds any that match, they’ll connect, and let you tell it what account to connect/link to for them. Aoki — providing a relay service. If their server got compromised, or a server in the middle, they could be compromised.
*   Securing these is so important. Vulnerabilities, whether known or not, can be gotten around. For example, christmas tree lights — you could turn the lights on for 12 hours and dry the tree, which would be devastating.


### Tools



*   [Brent’s cart of tools/things he’s included in his workbench](https://www.amazon.com/hz/wishlist/ls/30SARZ7RESBLJ?ref_=wl_share). \
If BrainGu wanted people to do microcontrollers and learning, and we wanted to have an office space with an electronics workbench, this is the kit for that.


### Practice



*   Research the device
*   Use it as “expected,” to get familiar with the expected result. Walk through the manual, whatever, to see how it works w/o any modifications.
*   Identify the components.
*   Identify debugging ports.
    *   What style of debug are they doing? Serial communication? Power, receiving transmit?
*   Dump the flash.
*   Extract/analyze the firmware.
*   Network communications
    *   Who is it talking to? Its own company or others?
    *   How frequently?
    *   Is it encrypting?
    *   Over what channels?
    *   What is it sending? Usage, IDs?

Once you have this whole frame/picture of the device, you can start influencing it. If you have a serial debugger, maybe no permissions on there, so root access. From a remote standpoint, you may not have anything. But if you have physical access, you have everything.



*   Same with malware. Start simple, get more invasive.
*   Everything goes in waves, especially with tech. If you go back 30 years ago, the internet was insecure. Then with worms and hackers and stuff you started protecting yourself. OS, AV, then encryption. They worked from necessity and need, basic to more advanced. So now major OSs are fairly robust and reliable, and difficult to exploit. Lots of thought in the process of security, then functionality, and then user friendliness.
*   Same very reactive cycle with IoT. Same thing happened with phones. Early ones were easy to exploit. Phones are encrypted at rest. 3-5 years ahead of that, you could plug in and dump (which is an exploit). IoT will do the same thing. At first they were wide open. More scrutiny now, and they’re going to find ways to make things more secure. Researchers have a difficult time analyzing their stuff. Same thing with video games. Switch, Xbox One… constantly looking for jailbreaks to run their own things. The more publicity, the more effort towards preventing that.
*   BrainGu has discussed getting into medical, automating medical security in a way that’s not invasive or detrimental. Programming with NFC (near field communications) is a way higher risk platform for medical, because human lives. It needs to be addressed more carefully than it is now. Brent thinks BrainGu could really help with that because they’re experts with the security first mindset. A pacemaker’s job is literally interfacing with the heart. If that pattern changes, can it sense that? Instead of people being focused on how they’re securing devices and being compliant, BrainGu’s approach to automation would free people up to make significant advantages (like an early warning system for heart attack).
*   There are a lot of ways to improve how medical devices can communicate better with their customers, and give them what they need. Those SMEs (medical device makers) should be able to focus on what the customer needs, and then build the solution with security embedded.
