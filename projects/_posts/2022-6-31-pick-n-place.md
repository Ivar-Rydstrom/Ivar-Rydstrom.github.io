---
layout: post
title: Pick-and-Place Device from a 3D-Printer
image: /assets/images/picknplace/picknplace.jpg
description: A precision Raspberry Pi controlled detector mounting solution reverse-engineered from a 3D printer.
category: projects
permalink: /projects/pick-n-place
related_posts: ""
tags: [engineering, computer science]
---
*The pick-n-place machine in lab at SLAC National Accelerator Laboratory*{:.caption}

## Pick-n-place

A pick and place (or pick-n-place) machine is a hardware machine typically used for automating the installation of surface mount components on PCBs. They are often also used in the field of experimental physics when precision is required to mount fragile detectors into housings. However, these machines are often prohibitively expensive.

At SLAC, I was tasked with finding a cheaper alternative to buying a full pick-n-place machine. In response, I designed my own using a 3D printer. My design borrows the frame and motor infrastructure from a [Prusa i3 MK3S+](https://www.prusa3d.com/product/original-prusa-i3-mk3s-3d-printer-3/) 3D printer, and replaces the extruder assembly with a custom suction-head to carefully handle the detector samples. It also features a USB microscope camera which allows the user to accurately position the detectors in the housings. The result is a fully-functional pick-n-place capable of mounting detectors with micron-level precision.

![camera](/assets/images/picknplace/camera.jpg){:.center-img style="width:65%;height:auto"}
*Microscope camera used for high-magnification observation mounted to suction head assembly.*{:.caption}

The pick-n-place is controlled entirely from an [Raspberry-pi](https://www.raspberrypi.org/). It handles all of the keyboard inputs to control the machine, and uses a board-mated relay module to toggle a tiny vacuum motor which provides suction. It also handles the stepper motor control of the three steppers providing the translational degrees of freedom native to the Prusa, and an additional single-axis rotation stage mounted on the bed to provide an extra degree of axial alignment.

![electronics](/assets/images/picknplace/electronics.jpg){:.center-img style="width:65%;height:auto"}
*Raspberry Pi control unit and pneumatic suction motor in custom 3D printed case.*{:.caption}

![Animation loading...](/assets/images/picknplace/animation.gif){:.center-img style="width:65%;height:auto"}
*Pick-n-place machine operated by SPLENDOR collaborator [Samuel Watkins](https://slwatkins.com/about/) in SLAC lab.*{:.caption}