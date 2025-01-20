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
![](/images/prg/sw1-boardsa.jpg)<br/>
(never mind the "dummy" sticker, that's my shenanigans)<br/>
![](/images/prg/sw1-boardsb.jpg)<br/>
All these boards share a common layout part: a BK7231N chip with 6 contact pads surrounding it.
This opens up a possibility to [use a jig](/sdsh/pogopinjig) for quick flashing of small batches of switches, which is great as single switches are probably the most common type of a switch around the house, so chances are you'll need more than one.
If you'll be making only a few switches or just don't want to make a jig, here's how to connect the switch for flashing.
As always in DIY, there are many ways to do it.<br/>
[![](/images/prg/sw1-padst.jpg)](/images/prg/sw1-pads.jpg) (click to enlarge)<br/>
**Attention!** RX and TX labels on pads describe where to connect them on your USB-UART adapter, not the actual RX/TX designation of the chip which are reversed. So if you see TX here - this is where to connect TX pin of UART, and RX denotes where to connect RX pin of UART.<br/>
Here are the pads we need to solder wires to. For RX and TX there are only a single spot to do so. With power and ground, however, there is a bit of freedom.
For GND connection choose whatever the easies for you is.
For power connection there are 2 options on these boards: 3.3 volts and 5 volts.

- If you have a USB-UART adapter with powerful enough voltage regulator (AMS1117) that can power up the board directly, then connect to **+3.3 pad** to the adapter's **3.3v output**.
- If you have a USB-UART adapter with weak voltage regulator or you are not sure, then connect **+5 pad** to the adapter's **5v output**.

CEN is a little special, it doesn't connect to the USB-UART adapter. Instead, solder a short piece of wire to it - you will need to briefly touch the GND pad with this wire at the beginning of the flashing process.


### Flashing double switches {#prg-double}

So far I encountered only one board layout for double (2-gang) switch. Here it is: [![](/images/prg/sw2_t.jpg)](/images/prg/sw2.jpg)<br/>
**Attention!** RX and TX labels on pads describe where to connect them on your USB-UART adapter, not the actual RX/TX designation of the chip which are reversed. So if you see TX here - this is where to connect TX pin of UART, and RX denotes where to connect RX pin of UART.<br/>
Unfortunately, there are no pads, so we can't use a jug here and the only way to flash it is to solder wires to the board.
Luckily it is not hard at all. All the contacts are easily accessible.

### Flashing dimmers {#prg-dimmer}

The only model of dimmer covered by this guide is the Avatto dimmer, which comes in 2 variations: 1-gang dimmer and 2-gang dimmer.
Both of them share the same board (or rather a 2-board sandwich) which looks like this:<br/>
![](/images/prg/dimmer-board.jpg)<br/>


![](/images/under-construction.png)
