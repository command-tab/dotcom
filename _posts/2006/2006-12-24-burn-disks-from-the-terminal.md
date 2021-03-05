---
layout: post
title: Burn Disks from the Terminal
---
While burning a CD image today, I discovered a really quick and easy way to do it from a Terminal window with zero hassle. Without launching Toast, Burn, Disco, or any of the myriad of point-and-click disc burning applications, you can simply type `hdiutil burn ~/Desktop/you/disk.dmg`. The burn begins immediately, with all default settings set as expected (max burn speed, verify on, etc.) It's not good looking compared to the alternatives, but memory usage is minimal, and it's a fast way to dump an image onto a disk if you're already working in the Terminal, or have a session open.

Aside from burning disks, `hdiutil` and its sidekick `diskutil` can do everything Apple's Disk Utility application can do, thus they have a very robust set of commands to choose from. Together, they can create, mount, and convert disk images, create and rebuild Mac OS X RAIDs, mount and eject physical disks, and even repair permissions. By typing `hdiutil` of `diskutil` at the command line, you'll be presented with the long list of options available for each program. Check them out -- you might just find a quick way to automate some of those tasks you do often.
