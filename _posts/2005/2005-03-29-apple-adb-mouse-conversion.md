---
layout: post
title: Apple ADB Mouse Conversion
---
Here's a little hack I did not long ago during the course of a weekend.  I opened up an old, blocky Apple ADB mouse and swapped the internals with that of a newer USB mouse.

![usb adb mouse](/assets/usb_finished.jpg)

Unlike today's injection molded, glued together, snap shut technologies, the Apple ADB mouse was no problem to open, with just had 4 standard Phillips screws on the corners of the underside.  With the mouse open, two small circuits are visible.  The circuit near the front of the mouse is where the pushbutton for clicking resides, and the other board tracks  mouse ball movement and the ADB interface.  Interestingly enough, the chip inside the Apple ADB mouse was made by Logitech, whose [2-button wheel mice](http://www.logitech.com/index.cfm/products/details/US/EN,CRID=2142,CONTENTID=5928) I swear by today.  I separated the two boards so that I could use the same pushbutton on the "new" mouse guts -- the Apple ADB mouse has a distinct click, and I wanted to maintain that classic feel after the conversion.

Opening the USB mouse (an IBM one I bought a while back but didn't like the feel of) was just as easy.  After locating the left-click pushbutton and tracing the wires to the main board, I marked the points with a permanent marker and cut the ribbon cables, separating the USB mouse's two boards as well.

![connected boards](/assets/usb_boards.jpg)

The next step was to combine the old Apple pushbutton with the main board of the USB mouse.  Since I marked the two points where the USB mouse was expecting a left-click switch to be attached, I soldered wires from the Apple switch to those points.  In hindsight, I should have checked and made sure that both switches (old and new) were normally open or normally closed, but I got lucky -- they matched.

![assembled components](/assets/usb_inside.jpg)

The hardest step in this whole hack was cutting the right size and depth hole in the bottom of the Apple mouse plastic so that the optics of the USB mouse could fit and work properly.  After much dremeling and hot glue, I was able to get the USB main board in a place that was stable and could "see" the desk.  After testing the optics and mouse pushbutton, it was time to close the little guy up.  I dug up a USB cable left over from another project that actually matched the Apple mouse color, attached it, and routed it through the hole used by the old ADB cable.  A little more hot glue to keep everything in place, and I closed it up and put the original screws back.  It's not very pretty on the bottom, but it works.  Not bad for a two or three hour weekend hack, I think.

![mouse underside](/assets/usb_bottom.jpg)
