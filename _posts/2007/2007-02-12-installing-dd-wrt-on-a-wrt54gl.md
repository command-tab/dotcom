---
layout: post
title: Installing DD-WRT on a WRT54GL
---
After running into continued troubles with my Linksys WRT54G v5 router, I decided to make a change in my network setup. In the past, I have had great success with Linksys devices, but lately I've found that my router keeps dropping packets, causing Safari to report "You are not connected to the internet." Updating the firmware on the router seemed to have no noticeable effect.

A while back, I had checked out some open-source firmware for Linksys routers called [DD-WRT](http://www.dd-wrt.com), and I decided to give it a shot. Unfortunately, the WRT54G v5 router has had some limitations imposed, both in memory and CPU speed, so that particular model is incapable of running the full DD-WRT installation.

Though Apple's recently updated AirPort Extreme base station will be shipping soon, I decided to replace my router with a new WRT54GL. The 'L' model has more resources to dedicate to the firmware. I like Apple's base stations, but I also value the web-based interface of nearly all other routers. Apple requires a Mac-only AirPort configuration program, and I like being able to make a quick change from a PC or Mac using just a simple web browser. The replacement I chose is also substantially cheaper than Apple's -- $65 vs $179.

Upon opening the box, I promptly set aside everything except the router itself and the power cable. To this day, I'm still not entirely sure what's on those CDs that come with them, as I just plug it in an configure it using a browser. The default Linksys firmware was the target for replacement, and here's a step-by-step rundown of what I did to overwrite it with DD-WRT.

1. Check the router's hardware version by looking at the sticker underneath. Version 1.1 is easer in that it does not require you to first load the 'mini' version to enable additional memory. Mine was v1.1, so I went straight for the DD-WRT v23 SP2 Standard generic" firmware.
1. Turn off AirPort on my PowerBook so that I'm not attempting to talk to the wrong router or over the potentially unstable wireless connection.
1. Plug into the new router via Ethernet -- Mac Ethernet to any router LAN port, 1 through 4.
1. Check the IP assigned to the Mac by opening System Preferences, Network, Built-in Ethernet, TCP/IP tab. It gave me 192.168.1.101, which is well within the standard .100+ DHCP range. DHCP looks to be working as expected.
1. Visit the WRT54GL administration interface by browsing to http://192.168.1.1 in Safari, logging in as admin/admin. Logged in successfully, everything seems to be working here, also.
1. To ensure the configuration is completely cleared, hold the small reset button on the back of the device for a full 30 seconds. Let it boot up again.
1. Re-visit the administration interface, and go to the Firmware Upgrade page.
1. Browse for the `dd-wrt.v23_generic.bin` firmware binary file, and hit Upgrade.
1. Wait for the device to re-flash itself and report complete. Don't touch that Continue button. Just wait 5 full minutes. Then unplug power from the router.
1. Hold the reset button again, while plugging power back in. Continue holding the reset button for 30 seconds, just like before. Let the router boot up once more (the power LED will stop flickering when it's booted).
1. Visit the new DD-WRT administration interface, again at http://192.168.1.1. The new login and password are root/admin.

So far, DD-WRT has proven very stable, and provides plenty of advanced controls. I might have to turn off DHCP on my old router and just use it as a 4-port switch!

**Update:** After several months of using DD-WRT full time, I'm happy to report that it's one of the most stable pieces of software I've ever used. It's provided outstanding router uptime and performance, with plenty of features. I'll be keeping it as my default firmware for the forseeable future!
