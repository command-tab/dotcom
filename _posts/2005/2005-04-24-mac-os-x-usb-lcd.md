---
layout: post
title: Mac OS X USB LCD
---
I'm working on a small project which will allow you to connect a small LCD to your Mac via USB, and I'm curious if people have any suggestions as to what they would use it for -- current iTunes track, unread mail, RSS headlines?

![usb lcd with text](/assets/usb_lcd.jpg)

![usb lcd breadboard](/assets/usb_lcd_breadboard.jpg)

The chip on the left is a Cypress USB interface from [Delcom Engineering](http://www.delcom-eng.com/products_USBIO.asp), and the one on the right is a standard MAX232 chip, which converts signal levels to RS-232 from the Cypress chip. Using these two together, you can send RS-232 data from your Mac, and I've connected it to a [serial LCD](http://www.seetron.com/bpp420_1.htm) from [Scott Edwards Electronics](http://www.seetron.com) (the most expensive part of the project), and am able to send any data to the LCD, even control the backlight!

I intend to build up a full page about how I did it in the very near future, but I'm still working on the C code which does the work of talking to the USB I/O chip.  Right now, though, I'm looking for suggestions of things to implement for the release.  I'll be working with a 4 line by 20 character LCD, if it helps.

![usb lcd components](/assets/usb_lcd_kit.jpg)

**Update:** Also, if anyone has a preferred way of getting data to the LCD, post that as well.  Would you prefer AppleScript, Python, something else?  I'm sure AppleScript will be involved somewhere along the way to communicate with Mac OS X apps, but what about the "glue" between that and my command-line app?  I'm partial to PHP, but it's not used very often as a system-level scripting system.
