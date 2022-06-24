# Background
I've been researching Chinese laser cutters for a couple of years. Ever since the k40 laser rose in popularity in the hacker scene (https://hackaday.com/2017/11/22/hacking-a-k40-laser-cutter/), these cheap Co2 lasers have fascinated me. I considered picking up a k40 for a while, but ultimately decided that the workspace was pretty limited for the types of things I would like to do. Around the beginning of 2019, the larger sized "red and black" or "yellow and black" 60w laser machines (https://hackaday.com/2020/12/11/putting-the-finishing-touches-on-a-60w-laser/) started making the rounds on youtube and maker news outlets.  These machines had dramatically more workspace than the k40, and in most cases came with most of the "must have" upgrades already installed (Ruida controller, upgraded stepper drivers, emergency stop, etc..). These machines represent a sweet spot on the Price:Performance continuum.  However they are still relatively low power and easily reach their limits when working with thicker materials.

## 1390
After another year or so of passive research, the next level in direct-from-china laser cutters have just started to emerge. These are known as "1390" machines. These machines are significantly larger with a 1200mmx900mm work surface and with laser tubes starting at 100w and going all the way up to 300w(!!!). These lasers represent the next step up in price bracket and capabilities, ranging between $5,000-20,000 depending on configuration options.   By the numbers, the 1390 machines are truly entry-level industrial machines and are able to be equipped with a lot of high end industrial features such as Auto Focus, CCD z-axis height following, Auto-focus, factory-floor status lights, etc.. What stood out to me the most is that the 150W+ models are capable of being equipped with a cutting head that will allow for cutting through up to 3mm of metal(!!). Once I discovered this I was sent down a deep dark rabbit hole on Youtube looking at how this could be. I learned that it was possible for these [relatively] low wattage machines to cut through mild steel, stainless steel, and aluminum by using what's known as "Oxygen assist" or "Oxygen mix". More on this later.

## The Journey Begins
Armed with the above knowledge, I started looking at everyone's favorite Chinese marketplaces (Alibaba, Aliexpress, Ebay, Amazon) and found a 180w model listed on Amazon for $7,700. Queue the Youtube search for "180w laser" to see what these machines are capable of. Spoiler alert: quite a lot actually.

So I ask the boss how we get one:

 ![slack approval thread](images/slack_approval.png)


As instructed, I followed it up with this email:

```
From: Tim Gast <xxx@xxxxxxx.xxx>
To: Spence <xxx@xxxxxxx.xxx>
Subject: Innovation Proposal (laser)

Spence, as discussed, below is my innovation proposal for a big blue laser cutting machine.  I should have *just* enough left in my education budget to cover it this year.

Propose: Procurement of 180w CNC Laser Engraving/Cutting machine.
https://www.amazon.com/dp/B08K2ZNJJM/ ($7,700 + tax, free shipping)
Additionally some software and a rotary axis to be purchased early next year after the laser arrives and I get the ground truth of what specific versions will work with this unit needed (total will be than $300 though)

Benefits:
A high-wattage, large footprint CNC laser will allow me to build the skillsets and understand the CAD/CAM software toolchain to support subtractive manufacturing operations. Including multi-step processes such as etching and cutting in a single software operation.
Also this will allow me to gain critical understanding of fabrication and manufacturing processes beyond common 3d printing (e.g. how different materials respond to various methods of manipulation), what levels of accuracy and tolerance are acceptable/expected.
All of this will pay dividends as BrainGu gets more involved in hardware and projects that include a physical component.

Additional benefits to Gu:
Creation or modification of physical items (e.g. prototypes) that are larger or more complex than what is possible on our existing fleet of 3d printers (e.g. Ralphie’s Rulers)
The ability to create custom swag on demand, including highly unique items that wouldn’t be possible/feesible through outsourced vendors (e.g. physical personalized “badges” for people)
The ability to utilize existing CNC machines (laser + 3d printer) to create additional CNC machines with different capabilities (CNC router, plotter, large-format 3d printers, etc..)
The machine identified is capable of processing the following materials:
Acrylic
Wood
Glass
Plastics
Crystal
Leather
Rubber
Stone
Ceramics
Additionally, according to my research, CO2 lasers >150w are capable of being modified win an oxygen assist to enable cutting steel up to 2.5mm
My education goals will be broken down in to the following phases

Phase 1:
Machine installation, calibration, & fine tuning.
Learning the skills necessary to successfully calibrate a large format high precision machine to 0.01mm accuracy
Producing “hello world” samples on both flat-stock and rotary axis
Installation and calibration of of LightBurn software with workspace camera

Phase 2:
Material experimenting
Produce some low-volume test pieces out the “feeds and speeds” as well as tolerances for various materials
Examples include:
Aluminum and steel business card blanks (powder coated, anodized and cermarked)
Challenge Coin blanks
BrainGu Pint Glasses
Hydroflasks and stainless tumblers

Phase 3:
Begin taking requests and producing items ad-hoc for the Greater-Gu
Begin designing and producing Badges for the team

Phase 4:
Upgrades
Begin pushing the limits of the machine and material capability by testing and installing upgrades and add-ons to enhance capability
Examples include:
Oxygen Assist for metal processing
Other upgrades as identified during previous phases


Thoughts?

Thanks,
  -Tim
```


You won't believe what happened next:

 ![approved](images/approved.png)
:partyparrot:

![ordered](images/amazon_ordered.png)

Now we get to learn about importing big things from China.


## Trials and Tribulations of ordering direct from China
First Message from the seller

![Message 1](images/amazon_message_1.png)

Ouch. 50 days puts me right at the end of January (30th to be exact). Oh well. I knew what I was getting in to. Boats are fun.

```
From: Tim Gast <xxx@xxxxxxx.xxx>
To: SFX-LYXC - Amazon Marketplace <xxxxxxxxx@marketplace.amazon.com>
Subject: Re: Amazon Order ID: 111-9835535-2246655

Hello.
Yes please send it.

  -Tim
  ```

Second Message from the seller

![Message 2](images/amazon_message_2.png )

 Wait a second... why do they need my EIN/SSN?! that seems shady AF!
 Off to google.

```
If the overseas supplier ships with an express carrier using a door to door service, the carrier has brokers to clear the goods on behalf of the ultimate importer. If a formal entry is required, CBP regulations require the broker to write the ultimate importer’s identification number EIN on the Entry Summary CBP Form 7501. The ultimate importer’s identification number is either the EIN/tax identification number assigned by the IRS or the importer’s social security number. A formal entry is usually required for commercial importations valued over $2,500.
```
*(source: https://shipcustomerdirect.com/overseas-supplier-requesting-tax-identification-number-ein)*

Ah. That makes some sense.  Plus an EIN isn't considered private (it's publicly searchable). Let's use that.

I still don't love that she's trying to take the thread out of Amazon's channels. That's a pretty common move for getting around buyer protection rules on these marketplaces.

```
From: Tim Gast <xxx@xxxxxxx.xxx>
To: SFX-LYXC - Amazon Marketplace <xxxxxxxxx@marketplace.amazon.com>
Subject: Re: Amazon Order ID: 111-9835535-2246655

Hello Julie,

Our EIN is: xx-xxxxxxx
Company name is: BrainGu, LLC
My email address is xxx@xxxxxxx.com so you can send the testing video and shipping information.

Thanks,
  -Tim
```

Third Message from the seller:

![Message 3](images/amazon_message_3.png)

Bummer..
Ok. Well, I guess I'll bump the thread out to email and keep diligent logs in case things go wrong.

```
From: Tim Gast <xxx@xxxxxxx.xxx>
To: julie@sfxlaser.com
Subject: Re: Amazon Order ID: 111-9835535-2246655

Hello Julie,

Here is my email address so that you can reply with the testing videos.

Thanks,
-Tim
```

```
From: Julie Lee <julie@sfxlaser.com>
To: Tim Gast <xxx@xxxxxxx.xxx>
Subject: Re: Amazon Order ID: 111-9835535-2246655

Hello Tim,
Thanks for your order,the tool kit will be sent to you as the gift.
Your machine will be shipped to the port to wait shipping space today.
The testing video and machine's picture will be sent to you next week.
```
![toolkit](images/toolkit.png)

*(The toolkit they're using to get around Amazon's buyer protections)*

```
By the way,since the machine is shipped by sea,but Amazon doesn't support SEA shipping number,I will upload the tracking number of your gift on Amazon.
Hope you could enjoy it.
Thanks
```

Damn. I figured this would happen, so it wasn't a surprise to me... Let's see how this plays out.


In other news, I was poking around the amazon listing and noticed this:
```
Q: How much does this machine weigh?

A: The size and the weight for this machine is 210*190*115cm 450KG.
Machine size is 184×142×105cm (72.5*55.9*41.3in)
Package size is 210*190*115cm(82.7*74.8*45.3in) 450KG(992LB).
```

**992lbs** Wooooo! thats a big ol' boy.  I think I'm going to need to invest in a set of pallet forks for the Bobcat to get this moved up the driveway and placed in the shop.



## 12.17.20 ##

```
From: Julie Lee <julie@sfxlaser.com>
To: Tim Gast <xxx@xxxxxxx.xxx>
Subject: Re: Amazon Order ID: 111-9835535-2246655

Hi Tim,
I attached the video of the machine as for your reference.
Also attached the  machine's pictures in attachment.

Testing Case cut 6.11mm MDF
https://youtu.be/dh-SlgHLaG8
 Testing Case of Cutting 9.41mm Acrylic
https://youtu.be/8AuL10MeQ40

About the tracking number,the machine will be sent to you by truck.There is no tracking number.
Once the machine arrive the port, the forwarder will contact with you to confirm the delivery time.
Here is the EXPORT CARRIER(Vessel)  ONE ARCADIA 054E
Bill of loading is PDLA201218R.

Any questions,pls feel free to let me know.
Thanks

Julie Lee
```

And thanks to the magic of AIS ([Wiki Link](https://en.wikipedia.org/wiki/Automatic_identification_system)) I can stalk the progress of my vessel!

I found the ship's schedule

![vessel_schedule](images/vessel_schedule.png)

Oh and I found a map showing it's live location and status!

![vessel_location](images/vessel_location.png "")


Creeping on the company's amazon profile I figured out that they're located in `Luoyang, Henan` which is inland a little ways, but looking at the vessel schedule is closest to `Qingdao` than it is to `Ningbo`. So it stands to reason that my machine is probably sitting at `QQCT (QINGDAO QIANWAN CONTAINER TERMINAL) 	Qingdao Qianwan Ctnr Tmnl Fenjin 4th Road Port Of Qianwan Huangdao Dist. Qingdao 266500` and slated to be loaded on to the ship around 12/20/2020.    Now the speculation about where in the US it will unload :thinking_face:  I'm thinking probably `TRAPAC LOS ANGELES`, but I need to internet stalk the facilities to see which one looks like it has greater capacity.  Hooray for OSINT!

Here are the images that were attached as a `.rar` file to that email.

## 12.17.20 ##
19:22 - The ONE ARCADIA has arrived in Quingdao! time to load up a laser.
The journey begins!

![moored in quingdao](images/moored_in_quingdao.png )

In other news, my $8,000 toolkit form Amazon arrived today.

![Fedex Package](images/toolkit_package.jpeg)

*(Fedex Air from China. That couldn't have been cheap)*

![Tool Kit](images/toolkit1.jpeg)

*(Big Quality. Such Sturdy. Very Color!)*

It's pretty cool that this cheap toolkit comes with a free 180w laser machine. :thinking_face:

# Long Dramatic Pause #
Imagine two months of checking AIS data multiple times per day, and snooping TRAPAC and Panda Logistics to try and find out more about the journey of my little laser...

It. Was. Awful.


## 01.21.2021 - Still waiting ##
```
From: Tim Gast <xxx@xxxxxxx.xxx>
To: julie@sfxlaser.com
Subject: Re: Amazon Order ID: 111-9835535-2246655

Hello Julie!

I hope you are well.
It looks like the ONE ARCADIA arrived in port a week ago.  I haven’t heard from the freight forwarder yet.

I know you said that the ports are busy so I was just wondering if you happened to be able to see any details of the status.  I am not able to see any information from Panda Logistics on the bill of loading that you sent (PDLA201218R).
Thank you! I’m very excited for this laser to arrive.

Thanks,
  -Tim
```

I'm sorry! I'm just impatient! :upside_down_face:

```
From: Julie Lee <julie@sfxlaser.com>
To: Tim Gast <xxx@xxxxxxx.xxx>
Subject: Re: Amazon Order ID: 111-9835535-2246655

Hello Tim,
The forwarder said they will contact you to appoint delivery time at the end of January.
More updates will let me know on next Tuesday.

Below is your local tracking information.
Chris,
Air Sea Transport Chicago Inc
610 Supreme Dr.
Bensenville, IL 60106
Phone# 847-298-8080 Ext 221
Email:mzhang@airseachicago.com

Thanks
Julie
```
Ok. I can work with that. It seems as though it actually is in LA. This is good news.

## 1.28.2021 ##
```
From: Tim Gast <xxx@xxxxxxx.xxx>
Sent: Thursday, January 28, 2021 12:29 PM
To: Chris Zhang <Mzhang@airseachicago.com>
Subject: Shipment tracking B/L: PDLA201218R

Hello,

I am hoping you can give me the status of a shipment that you are brokering for me.
Bill of loading is PDLA201218R - It was shipped via the ONE ARCADIA and should have arrived in Los Angeles on January 14th.

Are you able to provide any information on the status of this shipment?  I tried to use the tracking on your website but it doesn’t seem to be functional at this time.

Thank you,
  -Tim
```
```
Hi Tim,

The shipment was delay at port terminal for many days due to port congestion. The container has been broken down at LA. And your shipment has been on its way to Dallas on 1/27. ETA Dallas warehouse is 1/29. I estimate the delivery day will be next week.

Can you double confirm ship-to address, contact person name and phone number? I will prepare for the final delivery.


Thanks and Best Regards,

Chris

Air Sea Transport Chicago Inc
610 Supreme Dr.
Bensenville, IL 60106
Phone# 847-298-8080 Ext 221
Fax#     847-298-9841
Email: mzhang@airseachicago.com
Website: www.airseachicago.com
```
# !! #

## 2.5.21 ##
Southeastern freight calls me and says they want to deliver tomorrow after 2pm!
**W000000000T!!**

## 2.6.21 ##
1400 - Start cleaning out the shop while listening to conference calls.

1500 - Air up the tires on the skidsteer so i'm ready to unload this 1100lb beast

1600 - I hate waiting...

1650 - uh. It's almost 5.  Nothing from the driver yet. i should probably call dispatch and see what's up.

...

...

```"... So I just called the driver and he didn't answer. But he never answers, so i called dispatch. They said his truck broke down earlier today and he wasn't able to complete his route.  I can get you scheduled for first thing monday morning between 8 and 10 am if that's okay?"```

![FUUUUU](images/fuuuuu.gif)


"Uh yea, that's ok. Let's get it here ASAP. Thank you!"

## 2.8.21 - LASER DAY!! ##
Longest weekend ever... Brutal.

Sure enough, at 0850 my phone rings and the driver tells me he'll be here in 20 mins. YAS!

![YUGE Crate](images/crate.jpeg)

*(Oh wow. That is a _BIG_ crate.)*

[![Unloading](images/laser_unloading.png)](https://youtu.be/4WePVnzq8vw)


*(Unloading. Yikes!)*

![Safely on the ground](images/on_the_ground.jpeg)

*(Safely on the ground!)

[![Unboxing](images/unboxing.png)](https://youtu.be/Ci1lAQ-KJ7Q)

*(About 3 hours worth of unboxing and setup in 23 seconds)*

Setup was remarkably easy. Thanks in no small part to the fact that I've spent the last two months watching every single video on youtube related to these 1390 machines.

After the unboxing and installation of the various pieces, I wheeled the machine to it's perminent home, hooked up the chiller, air compressor, and exhaust fan, and immediately started ~~trying to blind myself~~ testing it.

![The best button](images/laser_power.jpeg)

*(Quite possibly the greatest button ever)*


![Lightburn Calibration Panel](images/lightburn_calibration_panel.png)

*(Luckily I'd previously built some handy-dandy calibration cards for testing material)*

[![Calibration Panel](images/calibration_panel.png)](https://youtu.be/-Gxhtce-l8w)

*(Here is the first run. so far so good.)*

[![frikking_lasers!](images/frikking_lasers.png)](https://youtu.be/w8buiHYojnE)

![calibration panel on pine](images/pine_calibration.jpeg)

*(It came out pretty well!)*


The first run came out pretty well.  The laser running at 100% power and 10mm/s speed on the outline is enough to _just barely_ cut through a 3/4" piece of pine.  I had to pop it out of the frame, but the edge came out pretty well.
You'll also notice some ghosting on some of the top lines. There was a slight issue with mirror alignment, so I went ahead and tuned up the mirrors and to try and improve the quality a bit.

![BrainGu](images/braingu.jpeg)

*(yeah, that'll do.)*

![Kid supervising](images/kid_supervising.jpeg)

*(My 10yr old definitely approves.)*

## Now lets test some more materials! ##
Future words and pictures about a stack of test cuts

## Doh! ##
Insert something about the broken lens and other... "accidents"  in here (there are a couple, like that time i caught the machine on fire)

### First failure ###
So there I was lasering a 4 foot tall BrainGu logo (it's okay @brent, you can be jealous), when suddenly the beautifully fine laser lines started to get a little thicker... then a lot thicker... then the plywood caught on fire (!!!)
That's weird.. I wonder why?


![Lens1](images/broken_lens1.jpeg)
Oh. That's why.

Turns out if your mirrors aren't aligned well (spoiler alert, mine weren't), the surface of the lens can get pretty hot and it will cause the lens to crack.  Which looks pretty cool.

![Lens2](images/broken_lens2.jpeg)
![Lens3](images/broken_lens3.jpeg)

So off to Amazon I go, to find a replacement lens.
Fun fact... while researching replacement lenses I learned that these focusing lenses are made of Zinc Selenide, which happens to be toxic to humans.  So I should probably stop playing with it while it's sitting on my desk.

Here's a video I found that gives a high level of what the lenses are made out of and why you should probably not eat them.

[![toxic_lens_video_link](https://i.ytimg.com/vi/-s8l7C2RyGw/hqdefault.jpg?sqp=-oaymwEbCKgBEF5IVfKriqkDDggBFQAAiEIYAXABwAEG&rs=AOn4CLCJGNV3GbyN_nCMnrUqAzg-rE3OOQ)](https://www.youtube.com/watch?v=-s8l7C2RyGw)

*(click me ^^ I'm a video)*

After a quick trip down Amazon lane, I found a suitable replacement lens that will fit my laser head and should keep all of my focal distances and settings the same.  This one came from Cloud Ray which is a pretty reputable purveyor of Chinese laser goods. $30 later and I'm back in action.

### Failure Number 2 ###
By this time, if you've been paying attention you'll likely have noticed the extremely sus targeting system.  The targeting system is a little red laser pointer that, in this case, is mounted on a bent piece of steel in such a way that it projects a visible red dot *roughly* where the laser is going to fire.  The problem here is science. When the work piece is more than 5mm away from the laser head, the visible dot is out of alignment from the actual laser head.   

![sus_targeting_system](images/sus_targeting_system.jpeg)

The whole thing is incredibly cheesy, and I also keep crashing it into things while I'm driving the laser head around with the manual controls.   

So off to cad I went to design an improved mounting solution that would mount two line lasers like crosshairs so that no matter how far the laser was from the workpiece, the intersection of the lines would always be the point of impact for the laser.  I wanted a unified system that would allow me to mount the auto-focus probe as well to keep everything nice and tidy.

![targeting_lasers1](images/targeting_lasers1.jpeg)
![targeting_lasers2](images/targeting_lasers2.jpeg)

*Beautiful!*

It's probably worth noting here, that when the machine arrived, the autofocus probe was missing the actual tip that makes contact with the work surface. I assume it rattled loose during shipping and fell out of the crate somewhere in the Pacific Ocean.

So, out came the calipers and cad software, and my 3d printer came to the rescue again and the autofocus probe was back in action!

![focus_probe_repair1](images/focus_probe_repair1.jpeg)
![focus_probe_repair2](images/focus_probe_repair2.jpeg)
![focus_probe_repair3](images/focus_probe_repair3.jpeg)

[![focus_probe](https://i9.ytimg.com/vi_webp/otyKLs2oRRY/mqdefault.webp?sqp=CPDQh4wG&rs=AOn4CLAhEN8x4maaGXGTeW8PkI40A-nMaA)](https://youtu.be/otyKLs2oRRY)

# Rotary#
Future words about my adventures in engraving round things (way harder than it sounds)

![BrainGu](images/rotary.jpeg)

[![rotary_doing_rotary_things](https://i9.ytimg.com/vi/klFHrXil7JA/mq1.jpg?sqp=CJTFh4wG&rs=AOn4CLBtjtcMbsMVvI8daIIAc8dUGDVR1A&retry=4)](https://youtu.be/klFHrXil7JA)

*(click me ^^ I'm a video)*

![brent_flask](images/hydroflask_rotary.jpeg)

Oh wait... what's this?? :grin:

![brent_flask](images/brent_flask.jpeg)


# Swag #
Pictures of cool stuff we've lasered.. (like Brent's laptop)

![BrainGu](images/BrainGu_flask.jpeg)

![brent_laptop1](images/brent_laptop1.jpeg)
![brent_laptop2](images/brent_laptop2.jpeg)

So we already know that engraving anodized aluminum is pretty easy... But what happens if I toss some a36 steel plate on the machine and turned it up to 11?
The results are actually pretty stunning. 0.0

![Engraving_on_steel](images/warning_sign.jpeg)
[![steel!](https://i9.ytimg.com/vi/Z3S0sQZKVrc/mq2.jpg?sqp=CMDHh4wG&rs=AOn4CLCjG2Dx1Orm9tDacQ0dFtOfMxSSBw)](https://youtu.be/Z3S0sQZKVrc)

*(click me ^^ I'm a video)*

![BZZZT!](images/bzzzzt.gif)

# Pumpkin #
In response to the 2021 pumpkin carving competition, and some gentle ridicule from @brent, I put together a quick video showing the process of going from image to finished product.

[![pumpkin_carving](https://i9.ytimg.com/vi_webp/lmp_CIJY244/mqdefault.webp?sqp=CIzJgYwG&rs=AOn4CLAY5F0MuURDL4I7Jk86VmkgWfokSA)](https://youtu.be/lmp_CIJY244)

*(click me ^^ I'm a video)*
