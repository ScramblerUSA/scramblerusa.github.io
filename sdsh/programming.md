---
layout: page
title: Programming guide
tags: []
project: sdsh
image:
  feature: prg/prg_f.png
---

First thing we need to do with any device is to program it, so it does what we need to do.

I want to emphasize: it is really the first thing to do as we won't have easy access to the contact pads in the later stages of the project.
Feel free to jump to the relevant part of the guide:
- [Setting up the environment](#prg-setup)
- [Creating a firmware](#prg-firmware)
- [Flashing single switches](#prg-single)
- [Flashing double switches](#prg-double)
- [Flashing dimmers](#prg-dimmer)

![](/images/under-construction.png)

### Setting up the environment {#prg-setup}

### Creating a firmware {#prg-firmware}

### Flashing single switches {#prg-single}

Single switches come in a variety of types.
Here are some most common board layouts covered by this guide: simple switch, switch with RF receiver, switch with power meter.<br/>
![](/images/prg/boardsa.jpg)<br/>
(never mind the "dummy" sticker, that's my shenanigans)<br/>
![](/images/prg/boardsb.jpg)<br/>
All these boards share a common layout part: a BK7231N chip with 6 contact pads surrounding it.
This opens up a possibility to [use a jig](/sdsh/pogopinjig) for quick flashing of small batches of switches, which is great as single switches are probably the most common type of a switch around the house, so chances are you'll need more than one.
If you'll be making only a few switches or just don't want to make a jig, here's how to connect the switch for flashing.<br/>
As always in DIY, there are many ways to do it. Here I'll describe the easiest to pull off.


### Flashing double switches {#prg-double}

### Flashing dimmers {#prg-dimmer}



![](/images/under-construction.png)
