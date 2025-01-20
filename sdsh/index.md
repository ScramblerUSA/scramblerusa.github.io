---
layout: archive
title: "SimpleDiySmartHome"
tags: []
image:
  feature: sdsh_feature.jpg
---

Here you will find everything you need to make your own inexpensive smart home devices that integrate with [Home Assistant](https://www.home-assistant.io/). This means no cloud! Everything works locally and you are in full control.
Don't be mistaken: DIY does not mean mediocre. By following this guide, you can build your own army of smart switches, dimmers, receptacles and other devices that not only work, but also look great.
Did I mention it's cheap?

## Why DIY?
Converting your entire house into a smart home is really expensive. I'd say it is cost-prohibitive for most of the people. While having 2-3-4 lights or switches automated is cool, having the entire house under control is way better. Making it not cloud-dependent is even better. This way you don't have to give away your information, create new accounts, manage those passwords. Also, your devices are controlled by your computer, so you are in charge. And of course, there is this pride you feel when you make something.

## Disclaimer
Making and installing these devices will expose you to hot soldering iron, fumes from flux, dangerous mains voltage, etc. This may harm your health, kill you, and burn your house down. By following this guide you agree to do so at your own risk.
This is not to discourage or to deter you. I'm not one of those who say "*if you don't feel comfortable doing it, leave it to the professional*", in fact I oppose this phrase, because if you don't push yourself beyond what's comfortable, you'll never learn to do these uncomfortable things. In my opinion it goes against DIY, so I encourage you to dive in the unknown and try to do what you've never done before. Just be aware of the risks involved.

## Requirements
Although it's super easy to follow this guide and make something, it is only true if you have certain equipment, parts and skills. Here's what you need:
 - A 3D printer capable of printing ABS and basic slicing/printing skills. A friend with a printer will do too!
 - A soldering iron (+consumables) and some basic soldering skills. [^1] Some fine soldering skills might be needed for more advanced devices.
 - Some basic tools: screwdriver, knife, sidecutters, etc.
 - Parts to perform the mods: switches, wires, LEDs, resistors, etc.
 - Positive attitude.

[^1]: Basic soldering skills: being able to solder a wire to a pad or a component on the board. It's really not that hard. Short photo-tutorial is available [here](howtosolder). You can do it!


### To be continued...
![](/images/under-construction.png)

#### Before you begin...
- [Sourcing tools](/sdsh/buytools/)
- [Sourcing smart devices](/sdsh/buydevices/)
- [Sourcing components](/sdsh/buycomponents/)

#### Device guides
- ~~[Getting the boards](/sdsh/teardown/)~~
- [Programming guide](/sdsh/programming/)
- [Switches and dimmers](/sdsh/switches/)
- ~~[Switch add-ons](/sdsh/switchaddons/)~~
- ~~[Smart plugs](/sdsh/smartplugs/)~~

#### Auxiliary stuff
- [Pogo pin jig](pogopinjig/)
- ~~[Plug opener jig](plugopenerjig/)~~


[File repository](https://github.com/ScramblerUSA/SimpleDiySmarthome)


---
#### Project updates

<div class="tiles">
{% for post in site.categories.sdsh %}
	{% include post-grid.html %}
{% endfor %}
</div><!-- /.tiles -->

All the things I share are always free. However, making them available (organizing, documenting, etc.) takes a lot of time. So, if you like what I'm doing please consider supporting me.
<a href="https://www.buymeacoffee.com/ScramblerUSA" class="btn" target="_blank"><i class="fa-solid fa-mug-hot" aria-hidden="true"></i></a>
