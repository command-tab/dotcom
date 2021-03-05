---
layout: post
title: iPod Junior
---
Back when Command-Tab first started, I did a hack where I managed to connect a full size hard drive to a 3G iPod. I'm happy to present today a much easier solution -- the "iPod Junior" -- using a laptop hard drive and a nearly pre-built adapter. The end result is an iPod with an attached 2.5" hard drive with next to no soldering.

![ipod junior attached](/assets/ipod_junior.jpg)

In my earlier hack, I noted that the 1.8" hard drive inside the iPod runs on 3.3v instead of the 5v used in slightly larger laptop drives. Again, some external power source will need to be connected to power the drive, as the iPod alone can't even spin up the laptop drive, much less a full desktop-sized drive. What I discovered is that the hard drive caddy inside IBM ThinkPad 240 laptops are almost a perfect iPod-to-laptop drive adapter, with the exception of power. On the front of the adapter is a female 1.8" hard drive plug normally used for connecting to the laptop bus, and on the back is a standard female laptop hard drive connector. With some slight modification to route in the correct power, this modified adapter can easily attach a laptop hard drive to your iPod's ribbon cable -- ready for formatting and use. 

![ipod junior adapter](/assets/ipod_junior_adapter.jpg)

To do the hack yourself, you'll need to acquire a ThinkPad 240 hard drive caddy off eBay, like I did. Cut the +3.3v power trace that leads to [pins](http://pinouts.ru/data/Ata44Internal_pinout.shtml) 41 and 42 on the 2.5" hard drive bus, and also scrape some of the green coating off both positive and ground traces. With the positive lines cut and some bare copper exposed on both traces, you can then solder on whatever power connector you prefer to run 5v to -- I used two simple pins from a pin header, as a floppy drive power connector will easily plug onto them. From there, connect everything up, power up the drive, and then the iPod. Format and use. Rinse and repeat.
