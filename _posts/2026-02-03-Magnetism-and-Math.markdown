---
layout: default
title: "Magnetism and Math"
date: 2026-02-03
categories: electrical
---
### Spark of Inspiration
One of my first "big boi" projects I wanted to start this year was...

**An EMP device~**

During DEFCON 2024, the embedded systems village was selling a badge that doubled up as an EMFI device, which I thought was extremely cool. 80% of my background is in electronics and tech, and seeing so many tech/iot focused villages during DEFCON reinspired me and showed me that cyber/hacking is more than doing HTB boxes and THM and such; while I love doing them and learning about web exploitation and pentesting, I was barely showing any improvement (and I was slacking quite a bit honestly), so seeing that my tech skills are also valuable when it comes to hacking was a breathe of fresh air, honestly this should've been obvious but better late than never!

*ANYWAYS* enough yapping about that, here's my research-

### Baby Electronics
Going into things, I knew the very very basics EMI and electromagnetism in general, too much of it can disrupt how electronics work for a variety of reasons: adding unwanted noise to the circuit, heat, disrupting transmissions, etc. But beyond that, I just knew generating my own electromagnetic field to mess around with electronics would be cool.

To start, I disassembled an old taser, added a coil to one end of the spark gap, adjusted the wiring a bit, and tested it out on some old iot devices I had laying around, and **BOOM** it worked. All devices that were near the coil while the taser was on started acting up or cut off completely!

So how do I harness this power? Well that's the complicated part-

So my idea was to recreate the high voltage from the taser using my own components, but my way of going about it was very *very* complicated. I've been studying transistors for a bit and wanted to implement an **SR Latch**; And I wanted to implement two different voltage "increase" circuits so that I could stick to using a 9v battery - a voltage multiplier and marx generator.

Now, a marx generator is a crazy idea, but it seemed reasonable at the time lol, as a spoiler alert though: I decided to go about a very different approach, but this is my thought process a month ago. So here's my original goal:

SR Latch controls two things: Voltage going into the multiplier, basically loading the gun - Voltage going out the multiplier into the marx gen, shooting the gun and creating that beautiful spark and emp blast.

Here's my original schematic in Kicad for the SR Latch and multiplier, looking back, *this is done very poorly*, but it was a somewhat of a start.

![My Original Voltage Mult Circuit]({{ "/assets/images/DownbadSchematic.jpg" | relative_url }})

### Correcting My Thinking
So where am I now, I recreated that diagram, well, ***an actual working version with some tweaks***, using my components at my work bench and was able to successfully multiply my 9v battery, I didn't create the marx gen because I was honestly nervous about it, but thankfully I didn't because I had some more efficient ideas.

So to end my progress post, **I learned some math-**

Alongside learning about the basic of electricity, magnetism, circuit basics, etc etc, I learned about two equations that'll aid me with plotting things out:

B(r) = NIA/r^3 : calculating the size of a magnetic field, double the current - double the size of the field
V = L(dI/dt) : calculating the voltage of a burst of current over a period of time

B = size of magnetic field
N = turns on the coil
I = current
A = area
r = distance


I'll figure out how to clean up equations for this site soon.

Both of these equations aid with figuring out how to manage the size and power of the magnetic field I plan on creating, it's surprising fun to think about and I'm excited to put it into practice. It'll be a minute before I start creating the circuit for testing these, I will need a MOSFET and some coils, a solenoid specifically, but for now I'll put a pin in this! On to the next thing for now-
