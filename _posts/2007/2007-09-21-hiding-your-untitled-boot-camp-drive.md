---
layout: post
title: Hiding Your "Untitled" Boot Camp Drive
---
After getting [back to Boot Camp](http://www.command-tab.com/2007/07/09/back-to-boot-camp/) from a dual-boot Mac OS X system, I remembered how disappointing it was that I couldn't rename the Windows NTFS volume from "Untitled" to something more appropriate. The [Garbage In Garbage Out blog](http://www.gigoblog.com/2007/03/07/boot-camp-hide-a-windows-xp-volume-on-mac-desktop/) has a tip that will accomplish the next best thing: Hide the Boot Camp volume from your Desktop.

Using the `SetFile` utility from the Developer Tools package that came with your Mac (on the second disc), you can effectively remove the volume from view in the Finder, while not affecting its normal operation or visibility anywhere else in the system. Great tip!
