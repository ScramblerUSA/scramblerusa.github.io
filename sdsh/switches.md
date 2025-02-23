---
layout: page
title: Switches and dimmers
tags: []
project: sdsh
---

Finally, we are at the assembly stage. At this point you should have all the parts ready and the board flashed with your firmware.

Please refer to the prior steps if you have something missing:
- [Getting the stuff](/sdsh/teardown/)
- [Programming guide](/sdsh/programming/)

##### In this guide

- [Printing the parts](#print)
- [Preparing the parts](#prep)
- [Assembling the device](#assembly)

### Printing the parts {#print}

To make a device you will need a specific set of parts to be printed. You can find all the models in STL format here: [https://github.com/ScramblerUSA/SimpleDiySmarthome/blob/main/3DModels/](https://github.com/ScramblerUSA/SimpleDiySmarthome/blob/main/3DModels/)
You don't need to print everything though! Here are the lists for each device:

- **Single switch**<br/>
  WallSwitch1.stl, WallSwitch2.stl, WallSwitch3.stl, WallSwitch4.stl, WallSwitch5.stl
- **Double switch (main on the left)**<br/>
  WallSwitch1-dbl-b.stl, WallSwitch2-2ch.stl, WallSwitch3-2ch-a.stl, WallSwitch3-dummy-a.stl, WallSwitch4-2ch.stl, WallSwitch5-2ch.stl, WallSwitch6-dbl.stl
- **Double switch (main on the right)**<br/>
  WallSwitch1-dbl-a.stl, WallSwitch2-2ch.stl, WallSwitch3-2ch-b.stl, WallSwitch3-dummy-b.stl, WallSwitch4-2ch.stl, WallSwitch5-2ch.stl, WallSwitch6-dbl.stl
- **Single dimmer**<br/>
  WallSwitch1-2btn.stl, WallSwitch2-dimmer2.stl, WallSwitch3.stl, WallSwitch4-dimmer2.stl
- **Double dimmer (main on the left)**<br/>
  WallSwitch1-dbl-2btn.stl, WallSwitch2-dimmer2.stl, WallSwitch3-dbl-b.stl, WallSwitch3-dummy-b.stl, WallSwitch4-dimmer2.stl, WallSwitch6-dbl.stl
- **Double dimmer (main on the right)**<br/>
  WallSwitch1-dbl-2btn.stl, WallSwitch2-dimmer2.stl, WallSwitch3-dbl-a.stl, WallSwitch3-dummy-a.stl, WallSwitch4-dimmer2.stl, WallSwitch6-dbl.stl

![](/images/under-construction.png)

- ~~**Dimmer with ceiling fan speed controller (main on the left)**: WallSwitch1-dbl-2btn.stl, WallSwitch2-dimmer2.stl, WallSwitch3-dbl-b.stl, WallSwitch4-dimmer2.stl, TBD~~
- ~~**Dimmer with ceiling fan speed controller (main on the right)**: WallSwitch1-dbl-2btn.stl, WallSwitch2-dimmer2.stl, WallSwitch3-dbl-a.stl, WallSwitch4-dimmer2.stl, TBD~~

 


### Preparing the parts {#prep}

Some smaller parts (WallSwitch4, WallSwitch5, and their variants) have built-in adhesion pads and supports - those need to be removed.
I designed them this way to simplify batch printing in ABS, which is prone to warping. While printing a full bed of parts I ran into the issue of just one part peeling off, knocking off half the parts like dominos.
I tried printing with a brim, but it is absolutely not needed for larger parts and cleanup is painful since the brim surrounds parts completely.
~~In case you are confident in your printer and don't want to deal with the cleanup, there are raw versions of those parts available.~~

If you like the look of a switch with a status LED, you need to drill a hole in the switch rocker.
Use the [switch dilling jig](https://github.com/ScramblerUSA/SimpleDiySmarthome/blob/main/3DModels/WallSwitch-DrillingJig.stl) to drill the hole in the right location.
Insert the jig into the rocker and use the 5/32 (or 4 mm) diameter drill to make a hole. Deburr the hole if needed, it needs to be smooth on the front side.
Take a piece of scotch tape and apply it on the front side. Make sure there are no air bubbles around the hole.
Use a plastic card or a fingernail if needed. Tape will contain the resin, while the adhesive will add a slight texture to the resin, giving it a matte appearance.
Add a drop of UV resin in the hole. Shine the UV light to harden it. Turn it over, remove the tape and shine the UV from the front for a good measure.


### Assembling the device {#assembly}

**Make sure you flashed the board before assembly!** Putting it in the case will make contact pads inaccessible, making wired flashing impossible.
Since assembly process relies on gluing parts together, the only way to access the board again is to carefully destroy the case without damaging the board.

General idea is the same across all types of switches. The board goes into the case (part #2) and is fixed in place with spacers (parts #4, #5).
At this point all the final solder connections can be made. The case is then glued to the frame (part #1).
Now the button is connected (3 buttons for 2-gang models). Finally, the remaining open frame is covered with a cover (part #3).
For 2-gang models there is also a large cover for the second switch frame (part #3-dummy) and a wire channel cover (part #6).


![](/images/under-construction.png)
