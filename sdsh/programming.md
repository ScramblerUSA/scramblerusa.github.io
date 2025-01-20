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
- [Single switch connections](#prg-single)
- [Double switch connections](#prg-double)
- [Dimmer connections](#prg-dimmer)
- [Flashing the chip](#prg-flash)
- [Flashing the dimmer MCU](#prg-dimmermcu)

### Setting up the environment {#prg-setup}

![](/images/under-construction.png)

### Creating a firmware {#prg-firmware}

![](/images/under-construction.png)

### Single switch connections {#prg-single}

Single switches come in a variety of types.
Here are some most common board layouts covered by this guide: simple switch, switch with RF receiver, switch with power meter.<br/>
![](/images/prg/sw1-boardsa.jpg)<br/>
(never mind the "dummy" sticker, that's my shenanigans, I like to label my devices to not mix them up)<br/>
![](/images/prg/sw1-boardsb.jpg)<br/>
All these boards share a common layout part: a BK7231N chip with 6 contact pads surrounding it.
This opens up a possibility to [use a jig](/sdsh/pogopinjig) for quick flashing of small batches of switches, which is great as single switches are probably the most common type of a switch around the house, so chances are you'll need more than one.
If you'll be making only a few switches or just don't want to make a jig, here's how to connect the switch for flashing.
As always in DIY, there are many ways to do it.<br/>
[![](/images/prg/sw1-pads_t.jpg)](/images/prg/sw1-pads.jpg) (click to enlarge)<br/>
Here are the pads we need to solder wires to.
**Attention!** RX and TX labels on pads describe where to connect them on your USB-UART adapter, not the actual RX/TX designation of the chip which are reversed. So if you see TX here - this is where to connect TX pin of UART, and RX denotes where to connect RX pin of UART.<br/>
For RX and TX there are only a single spot to do so. With power and ground, however, there is a bit of freedom.
For GND connection choose whatever the easies for you is.
For power connection there are 2 options on these boards: 3.3 volts and 5 volts.

- If you have a USB-UART adapter with powerful enough voltage regulator (AMS1117) that can power up the board directly, then connect to **+3.3 pad** to the adapter's **3.3v output**.
- If you have a USB-UART adapter with weak voltage regulator or you are not sure, then connect **+5 pad** to the adapter's **5v output**.

CEN is a little special, it doesn't connect to the USB-UART adapter.
Instead, solder a short piece of wire to it - you will need to briefly touch the GND pad with this wire at the beginning of the flashing process. This is optional.

With all wires soldered it should look something like this: [![](/images/prg/sw1-wired_t.jpg)](/images/prg/sw1-wired.jpg)

Now that we are done with connections, it is time to [flash the chip](#prg_flash).


### Double switch connections {#prg-double}

So far I encountered only one board layout for double (2-gang) switch. Here it is:<br />
[![](/images/prg/sw2_t.jpg)](/images/prg/sw2.jpg) (click to enlarge)<br/>
Unfortunately, there are no pads, so we can't use a jig here and the only way to flash it is to solder wires to the board.
Luckily it is not hard at all. All the contacts are easily accessible.
**Attention!** RX and TX labels on pads describe where to connect them on your USB-UART adapter, not the actual RX/TX designation of the chip which are reversed. So if you see TX here - this is where to connect TX pin of UART, and RX denotes where to connect RX pin of UART.<br/>

For RX and TX there are only a single spot to do so. With power and ground, however, there is a bit of freedom.
For GND connection choose whatever the easies for you is.
For power connection there are 2 options on these boards: 3.3 volts and 5 volts.

- If you have a USB-UART adapter with powerful enough voltage regulator (AMS1117) that can power up the board directly, then connect to **+3.3 pad** to the adapter's **3.3v output**.
- If you have a USB-UART adapter with weak voltage regulator or you are not sure, then connect **+5 pad** to the adapter's **5v output**.

CEN is a little special, it doesn't connect to the USB-UART adapter.
Instead, solder a short piece of wire to it - you will need to briefly touch the GND pad with this wire at the beginning of the flashing process. This is optional.

Now that we are done with connections, it is time to [flash the chip](#prg_flash).


### Dimmer connections {#prg-dimmer}

The only model of dimmer covered by this guide is the Avatto dimmer, which comes in 2 variations: 1-gang dimmer and 2-gang dimmer.
Both of them share the same board (or rather a 2-board sandwich) which looks like this:<br/>
![](/images/prg/dimmer-board.jpg)<br/>
These by far are the most difficult to work with. I'll cover a few ways to connect to both the WiFi chip and MCU chip.

If you have the proper equipment (see the [tools buying guide](/sdsh/buytools) for T12 station and tips), then you can desolder the WiFi module and the rest is trivial.
You can also use solder-sucking desoldering gun if you have one.
<div style="font-size: 0.8em">
There is also a technique to desolder multileaded things: you need to solder a piece of thick copper wire across the leads first.
Then heat it with powerful soldering iron, this copper wire will spread the heat across all the leads.
Once the solder liquified on all the leads, pull out the module and wipe the copper wire off the board with the iron.
Lastly, clean everything up with the desoldering wick.
</div>

Once desoldered, you can easily connect to the pins of the module: [![](/images/prg/dimmerd-connect_t.jpg)](/images/prg/dimmerd-connect.jpg)
I recommend using IC clips (see [tools buying guide](/sdsh/buytools)) to quickly connect and avoid soldering altogether.
**Attention!** RX and TX labels on pads describe where to connect them on your USB-UART adapter, not the actual RX/TX designation of the chip which are reversed. So if you see TX here - this is where to connect TX pin of UART, and RX denotes where to connect RX pin of UART.<br/>

If you are unable to desolder the module, do not fret! There is another way.
We need to cut one of the pins to disconnect MCU line so it doesn't interfere with the flashing process.
Using your side cutters, snip the second pin in the middle: [![](/images/prg/dimmer-cut_t.jpg)](/images/prg/dimmer-cut.jpg)
Then snip it again to cut a tiny piece off: [![](/images/prg/dimmer-cut1_t.jpg)](/images/prg/dimmer-cut1.jpg) so the pin parts do not touch each other.
This is how NOT to do it: [![](/images/prg/dimmer-cut1w_t.jpg)](/images/prg/dimmer-cut1w.jpg) - as you can see despite being cut, parts of the pin still touch each other.
This is enough for MCU to send a signal and disrupt the flashing process.

After you cut the pin, connect the clips: [![](/images/prg/dimmer-connect_t.jpg)](/images/prg/dimmer-connect.jpg) or solder the wires.

Now that we are done with connections, it is time to [flash the chip](#prg_flash).

##### MCU connections

If you want to add the ceiling fan control to the dimmer or just want to replace the stock firmware, here's how to connect.

If you desoldered the module, connection is pretty trivial: [![](/images/prg/dimmerd-mcu-connect_t.jpg)](/images/prg/dimmerd-mcu-connect.jpg)
On this picture you can see the UART connection as well as a wire soldered to PIN5 connecting it to +3.3V. This is some very fine soldering.
Alternatively you can use the resistor method described below.

**Attention!** RX and TX labels on pads describe where to connect them on your USB-UART adapter, not the actual RX/TX designation of the chip which are reversed. So if you see TX here - this is where to connect TX pin of UART, and RX denotes where to connect RX pin of UART.<br/>

If you can't desolder the module, there is an alternative solution again!
Only this time we need to cut 2 pins: [![](/images/prg/dimmer-cut2_t.jpg)](/images/prg/dimmer-cut2.jpg)
After that we can connect using IC clips or by soldering the wires: [![](/images/prg/dimmer-mcu-connect_t.jpg)](/images/prg/dimmer-mcu-connect.jpg)
However, we still need to provide the +3.3V signal to the PIN5 of the MCU to put it into the boot mode: [![](/images/prg/dimmer-mcu-pin5_t.jpg)](/images/prg/dimmer-mcu-pin5.jpg)
This pin is not easily accessible as the module covers the MCU chip. So we will use the resistor method.

##### The resistor method.

PIN5 is the pin responsible for putting the MCU into boot mode, so we can reflash it.
Lucky for us both neighboring pins are not used and are configured as inputs by default, so we can connect them without fear of burning the chip.
To do this we will need a resistor. Anything between 1K and 10K should work just fine. I used 10K in my experiments.
Solder a wire to one side of the resistor. Then solder another end of the wire to +3.3 volt on the board.
Easily accessible locations are the +3.3 pin of the module and the right side of the LED resistor. Bend the other resistor lead in L-shape.
Now you can touch the PIN5 with it without worry - you won't fry anything: [![](/images/prg/dimmer-mcu-boot_t.jpg)](/images/prg/dimmer-mcu-boot.jpg)
It's OK to touch PIN4 or PIN6 as well, no harm will be done.

After flashing is done, you can easily repair the cut pins with some solder and flux:
[![](/images/prg/dimmer-repaired_t.jpg)](/images/prg/dimmer-repaired.jpg)


### Flashing the chip {#prg-flash}


![](/images/under-construction.png)


### Flashing the dimmer MCU {#prg-dimmermcu}

![](/images/under-construction.png)

