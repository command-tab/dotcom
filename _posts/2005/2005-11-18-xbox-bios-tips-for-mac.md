---
layout: post
title: Xbox BIOS Tips for Mac
---
For those working on a Mac doing Xbox modifications, here's a tip for handling BIOS files.  Some Xboxes, such as the "version 1.0," require a 1 MB sized file, but not all are distributed this way.  On the Windows side of things, there are a number of tools available for dealing with Xbox BIOSes, however there's nothing specifically made for Mac.  With a little bit of command-line work, you can combine files without any special tools except the operating system.  To join files, the general syntax is:

    cat bios512KB.bin bios512KB.bin > bios1MB.bin

You're simply doubling over the file to obtain the 1 MB sized one the Xbox needs. It can be repeated four times for a 256 KB BIOS. Or, if your Xbox is wired with a switch into multiple banks, you could combine two separate files using `cat` and the redirection operator `>` to build a custom BIOS, and switch between them as needed.

While I haven't tried, I'm sure the Unix 'split' utlity can slice a file and do the reverse of the above (something along the lines of `split -b 512k bios1MB.bin`).  Just be careful, as not all BIOSes are designed to be sliced into smaller pieces.  Hopefully these two built-in tools should get you through any Xbox BIOS issues on the Mac.
