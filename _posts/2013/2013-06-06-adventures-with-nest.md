---
layout: post
title: Adventures with Nest
categories: docs
---


I recently purchased a pair of [Nest Learning Thermostats](https://nest.com) for my new home. Compared to the white brick style Honeywell thermostats that came with the place, the Nest is so much more advanced. It does temperature learning, auto-away, and remote control over Wi-Fi from the web and iOS devices. It also has a color LCD and just generally looks beautiful on the wall with its brushed stainless steel housing.

![nest thermostat](/assets/nest.jpg)

Installing the Nest is pretty straightforward with a modern forced air heating and cooling system:

* Remove the old thermostat and mounting plate from the wall
* Disconnect the wires
* Patch and paint any holes
* Install the Nest mounting base and connect the wires
* Pop the Nest onto the base and configure the software

My initial install went well physically, but not long after, I discovered that the Nest would regularly run out of battery power. I quickly learned that due to how the HVAC circuits are arranged, the Nest can only draw power while the system is running. When the system is not busy heating, cooling, or running the fan, the Nest is left to run under its own battery power. And in sunny California during the springtime, the system doesn't run often enough to let the Nest keep a charge. Several times per day, I would have to unplug the Nest from its base and charge it over micro USB. Not a great solution.

Reading more about the Nest and HVAC circuitry, I found that there is a solution for situations like this. A "common wire" that provides a path back to the HVAC controller would allow the Nest to draw the power it needs while not running any systems. As luck would have it, my system provided this common wire, but connecting it to the Nest had no effect on the battery. More telling was the fact that the Nest did not detect that the wire was connected.

So, I decided to find out what was at the other end of that common wire. I put up a ladder and ventured into the attic of my home and scouted around the furnace. On top of it, inside an easily-opened metal enclosure, was the thermostat controller, a ZTech ZTE2S. Double checking the [wiring diagram](/assets/zte2s_wiring.pdf) and comparing it with the wires on the left (coming from the Nests), it's clear that the blue common wire is simply not connected to the controller. In the photo below, you can see that it's clipped short, close to the brown jacket covering the bundle of five wires.

![wiring before with blue wire disconnected](/assets/nest_before.jpg)

Reconnecting the wire was a matter of disconnecting the wires that were already connected, snipping them all to the same length, and stripping a little plastic off the end so that all five can be connected to the HVAC controller.

![wiring after with blue wire connected](/assets/nest_after.jpg)

A few hours after leaving the Nest installed with the common wire attached and the HVAC controller all closed up, its battery has fully charged and the features work great.
