---
layout: post
title: Boot Camp Drivers for iMac (Early 2009)
---
Apple's newest iMacs are a fast set of machines and run Windows faster than any PC I've ever used, but unfortunately, Apple has yet to update Boot Camp with the required drivers to support the latest and greatest components. Mac OS X ships with the necessary software and works as expected, but Windows XP is met with some trouble. Right away, you'll notice that your graphics resolution is set to a paltry 800x600, and you have no sound output as well. Here's how to get those systems working until Apple can provide an "official" fix:

**Graphics Drivers**

Visit [nVidia](http://www.nvidia.com) and download the "GeForce 9M Series (Notebooks)" driver package, as this is graphics chipset in the Early 2009 iMacs. Run the downloaded setup utility, next-next-nexting your way through the steps, and reboot at the end when prompted. Upon restart, you'll be able to properly max out your display to the iMac's native resolution.

**Audio Drivers**

Boot Camp 2.1 actually ships with RealTek HD audio drivers, as evidenced by the lack of a yellow exclamation mark for this system in Windows' Device Manager, but they don't seem to work properly, since there's no sound output. Visit [RealTek](http://www.realtek.com.tw/downloads) and download the "High Definition Audio Codecs" driver package for your OS. In this instance, I downloaded "Windows 2000, Windows XP/2003(32/64 bits) Driver only (Executable file)", since I'm running Windows XP Pro SP2. Run this setup utility as well, rebooting again when done. After restarting, you should be greeted with Windows' standard login sound, confirming the install worked.

**Update:** The Mac OS X 10.6 Snow Leopard disc includes Boot Camp drivers for these iMacs. The Snow Leopard disc is a hybrid image: it provides the Mac OS X installer when viewed under a Mac OS X system, but shows Windows drivers when viewed in Windows. Just run the setup in Windows right off the disc, and you should be set.
