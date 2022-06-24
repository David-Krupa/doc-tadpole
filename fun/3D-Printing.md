<img align="right" src="https://github.com/braingu/tadpole/blob/master/images/TLP/TLPAmber.png">

Check the slack channel #fun-3dprinting for all the latest and best.

## Why?

*   Community was cool
*   More consumer-friendly versions of printers. You don’t need to know everything about them to make them work any more.
*   At the time, BrainGu was looking to get involved in [cubesats](https://en.wikipedia.org/wiki/CubeSat). They thought they should be able to make their own mockups, so that was justification.
*   Tried a few different pieces of software, and started making random things.
*   More of a creativity / spark outlet than anything else. Change of pace and refresh.
*   Brent makes little boats, lego pieces, minecraft figures, rc cars (snow tires! Skis! Replacement parts, 5th wheel hitch trailer). Also a quilting ruler for his mom. Idea to product in two hours (seizing the means of production).
*   Socio-cultural impacts of being able to make things
    *   Maker culture
    *   DIY mindset


## Getting Started

*   Good review of printers/intro: [https://www.youtube.com/watch?v=nb-Bzf4nQdE](https://www.youtube.com/watch?v=nb-Bzf4nQdE)
*   [Ender3 Pro](https://www.creality3dofficial.com/products/creality-ender-3-pro-3d-printer) is the best starter printer. Good reviews, widely supported, gives you good quality, bang for your buck. $250. Biggest thing Brent’s noticed with cost in relation to what you get -- all printers can give you a good result, but the more you pay, the easier it is to use.
*   The more expensive ones have better support, and easier access to print things. You could print immediately with the [TAZ 6](https://www.lulzbot.com/store/printers/lulzbot-taz-6). Brent's [Delta](https://all3dp.com/1/delta-3d-printer-best-3d-printers/) cost $100, but it took months of knowledge and effort.
*   We’re on the downward slope of barrier to entry. With more companies coming out with easier to use and assemble systems, it’s making the curve lower. Systems are becoming more compact, more consumer friendly, and only going to get better. New advancements are going to be using different materials for printing, and different applications.
*   The tutorials and models available are good. [https://www.thingiverse.com/](https://www.thingiverse.com/) is literally download-and-print, which makes it easier for people to make use of having a printer. No CAD experience, no design experience, just download and print.


### Machines

Four main styles — Each style has pros and cons and different ways you’d use them and why.



*   **Cartesian style** &mdash; bed moves forward and backwards
    *   Easiest to get, cheapest, more entry level.
*   **Core XY printers** &mdash; bed stays fixed, the extruder head moves in x&y, and then the bed lowers to account for z
    *   More stable, you can print faster, take up less space
*   **Delta style** &mdash; 3 pillars, extruder in the middle, uses triangles (deltas) to figure out where to go.
    *   Super fast and fancy and cool looking
*   **Resin printers** &mdash; still fused filament, but slightly different. Plate lowered into a vat of uncured resin. Image projected with UV light that cures the resin in that spot. Very futuristic.
    *   You can do more difficult and exotic objects and items. Because no previous layers requirement, you can print unsupported objects easier.


### Filament

The plastic used by the printers. 4 main types



*   **PLA** &mdash; general-purpose plastic. Really easy to print with, clean and easy results, sticks to the build plate well. Lower temp printing. Very rigid, not much flex.
*   **ABS** &mdash; a little more difficult to print. More susceptible to its environment. If you have a crossbreeze, it's a problem. Little more difficult to tune it in, but you get high quality parts. Impact resistant. Better with high quality chemicals. Very useful and durable. Very easy to get.
*   **PETG** &mdash; mix between the two. High temp and chemical resistant. Semiflexible. Can take more impact and give. Fairly easy to get to print. Have to have a special machine/extruder because of the higher temperature. Really good results when you get it dialed in.
*   **TPU** &mdash; very soft and flexible filament. You have to have a specific type of printer, (direct drive). Use for gaskets and sealers and stuff.

There are lots of different types of plastics for different applications. Some are more flex, more chemical resistant, or have different properties.

Look up common plastics and their properties. Start with what you need it to do, and then Google it. PLA, ABS, TPU… PETG. Most common. Each one is different. More exotic filaments are available. Plastic is available on Amazon. $20 for 5KG.


### Extruders

*   **Direct drive** &mdash; where the motor that pushes the filament thru the nozzle, is connected to the hot end and nozzle. Drive is heavier, which is a downside because it can't move as fast but it allows you to print softer filaments.
*   **Bowden drive** &mdash; extruder motor is fixed somewhere else away from the nozzle and has to push (“Pushing a rope”) a longer distance. Benefit is that it’s easier to make the extruder head lighter and easier to set up. Downside is that it has more pushed filament to the extruder. The extruder can move faster but can’t do the more exotic filaments.
*   Slicer builds out the plan for the 3d printer. Speed, filament type, etc, all get configured there. The slicer translates those to the object as it prints them. Take the slicer output to the printer, the printer makes it.


### Templates/Patterns

*   [Fusion360](https://www.autodesk.com/products/fusion-360/overview), (CAD) but there are a bunch of other ones. [SketchUp](https://www.sketchup.com/), [openSCAD](https://www.openscad.org/)
*   A lot of guessing and fumbling through. A lot of the advanced features, you can find on YouTube or Google or whatever.


## Use Cases

*   Working in the physical space.
*   Bid on a project bidding on last year, for shipping docks. They wanted a system that would watch the rope and look for signs of wear. So they were to create a machine learning system that could identify the spots, and automate the process. They sent a bunch of pictures of worn rope. So BrainGu wrote code that would tell you what the levels of wear were, take pictures, analyze them, and then go fix that one spot. Proof of concept of how we could set up a camera. We 3D printed the camera mount setup for the camera. Minimum changes to existing systems.
*   Swag items for BrainGu. Brent made a BrainGu nightlight by combining a 3D printed object with resin epoxy.

<p align="center">
  <img src="https://github.com/braingu/tadpole/blob/master/images/gunightlight1.png" alt="BrainGu nightlight -- blue lion rampant" width="500">
  <img src="https://github.com/braingu/tadpole/blob/master/images/gunightlight2.png" alt="BrainGu nightlight -- orange BrainGu logo" width="500">
  <img src="https://github.com/braingu/tadpole/blob/master/images/gunightlight3.png" alt="BrainGu nightlight -- BrainGu logo backlit" width="500">
</p>

*   Fascinated by Dyson bladeless fans. So Brent wanted to make his own (because that’s what a rational person would do).
*   Printed up a bunch of mask holders, and handed those out to everyone. Had to be flexible, durable.


## Impacts

*   In Italy, they printed ventilator valves. Very cool community thing. I don’t think it’ll replace manufacturing, because not everyone wants to maintain their machines. But it’s a great way to prototype and demonstrate.
*   Metal 3D printing. Right now, they have powder, which gets fused with a laser. Brent would like to see that be more consumer friendly. Porsche is 3D printing piston parts; design, print, lathe, etc, and then put in an engine and test. Lighter, less material, leads to a lot of benefits. Changing how they make engines makes them more efficient. It’s going to speed up and revolutionize how we approach prototyping. We can make iterative design changes and test them through at low cost in flexible ways.
*   He hopes makerspaces will help people think about how they do things in the physical space. From a community standpoint, any time people are coming together to improve things, it makes things better. Teaches people different skills, different approaches.
*   A few years ago, Brent’s local high school was asking for donations for the robotics teams. He got BrainGu to donate money and he donated time to help the kids build their robots. Some were interested in programming, electronics, physical design. Every space was accounted for, which allowed the kids to explore.


## 3D Printing @ BrainGu

Maj. Brad “Ralphie” Short needed a see-through ruler/level. Tim and Brent designed and mocked it up. Printers are limited by bed space, but Ralphie wanted a 48” thing, rather than the 12” they’re capable of currently. He wanted a single piece, rather than together. Tim Gast has a router, and can do aluminum that can do any length.

### Ruler pictures

<p align="center">
  <img src="https://github.com/braingu/tadpole/blob/master/images/widowruler1.png" alt="Widow-branded ruler template" width="500">
  <img src="https://github.com/braingu/tadpole/blob/master/images/widowruler2.png" alt="Widow-branded ruler template side-on" width="500">
  <img src="https://github.com/braingu/tadpole/blob/master/images/widowruler3.png" alt="Widow-branded ruler template" width="500">
  <img src="https://github.com/braingu/tadpole/blob/master/images/widowruler4.png" alt="Widow-branded ruler template" width="500">
  <img src="https://github.com/braingu/tadpole/blob/master/images/widowruler5.png" alt="Widow-branded ruler template" width="500">
  <img src="https://github.com/braingu/tadpole/blob/master/images/widowruler6.png" width="500">
  <img src="https://github.com/braingu/tadpole/blob/master/images/widowruler7.png" width="500"><img src="https://github.com/braingu/tadpole/blob/master/images/widowruler8.png" width="500">
  <img src="https://github.com/braingu/tadpole/blob/master/images/widowruler9.png" width="500">
  <img src="https://github.com/braingu/tadpole/blob/master/images/widowruler10.png" width="500">
  <img src="https://github.com/braingu/tadpole/blob/master/images/widowruler11.png" width="500">
  <img src="https://github.com/braingu/tadpole/blob/master/images/widowruler12.png" width="500">
</p>
