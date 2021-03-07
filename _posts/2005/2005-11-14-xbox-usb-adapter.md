---
layout: post
title: Xbox USB Adapter
---
Here's a quick Xbox hack I did a long while ago when the _007: Agent Under Fire_ exploit first debuted.  The hack called for an Xbox memory card or a USB flash drive to transfer the files.  At the time I did not own a memory card, as the Xbox ships with an 8 GB internal hard drive for storing game saves and caches.  However, I did have a 32 MB USB 1.1 flash drive, which is small by today's standards.  I had read that the Xbox would easily format most flash-based media, so I decided to build a little adapter.  Internally, the Xbox uses USB for all its controller I/O, including the overpriced, low capacity memory cards.

![xbox usb adapter](/static/xbox_usb_finished.jpg)

To build this adapter, I purchased an extra $5 breakaway cable replacement, cut the cord in the middle, and snapped open the green plastic connector.  You could also use the same piece from an existing controller.  Regular computer USB cables have four wires in them, but the Xbox has a fifth for powering light guns and other devices -- its wire stands out a bright yellow.  [Jameco](http://www.jameco.com) sells the necessary female USB A connector, but one can be acquired more quickly by de-soldering one from an existing device.  In my case, this was a dead USB hub.  Following a pinout of the USB standard, I soldered the appropriate wires to the matching color of the Xbox connector, simply skipping over the yellow wire.

![xbox usb adapter insides](/static/xbox_usb_pins.jpg)

To finish up the hack, I fit the whole assembly into the original Xbox controller plug with a little Dremel work.  (What hack would be complete without a Dremel?)  Only a small few bits of plastic at the end needed to be removed to fit the USB connector into the space where the cord used to protrude.  The halves can be snapped or glued together to hold the plug secure.  The finished adapter can connect USB flash drives, keyboards, and mice to the Xbox.  A hub can also be attached to use all three within Xbox-Linux.

![xbox usb adapter and enclosure](/static/xbox_usb_shell.jpg)
