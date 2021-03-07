---
layout: post
title: SmartJoy FRAG Insides
---
I recently purchased an Xbox [SmartJoy FRAG PS/2 adapter](http://www.lik-sang.com/info.php?category=53&products_id=5438&) to try it out, with the hopes of gaining some extra precision in Halo 2 (which I play less and less as my interest in Xbox modification grows). The SmartJoy does more than just connect the devices together -- it actually emulates the signals an Xbox controller would be sending when you use the keyboard and mouse for movement. It allows you to play games on the Xbox as if it were a desktop computer game, moving around using the WASD key setup and mouse clicking for firing. While my long-range shots in Halo became much more accurate, close-combat and vehicle control suffered greatly. For now, I've switched back to my standard Xbox "S" controller.

Because I was curious how it worked, I opened up the SmartJoy to see what makes it tick.  It's nothing more than a Cypress USB chip and a programmed PIC microcontroller.  The USB chip speaks the proper protocol to the Xbox (as the controllers and memory units are all just USB devices in disguise), and the PIC handles key programming and PS/2 interfacing.  All in all, it's a pretty neat little gadget, but not quite worth the $35 plus shipping from Hong Kong.

![smartjoy frag insides](/static/xbox_smartjoy_frag_insides.jpg)
