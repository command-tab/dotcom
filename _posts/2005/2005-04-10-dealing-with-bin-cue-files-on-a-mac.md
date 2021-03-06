---
layout: post
title: Dealing with Bin/Cue Files on a Mac
---
Once in a while you run across CD images in the format of a `.bin` file and `.cue` file. These are CDRWin images which can't (as far as I know) be easily read on the Mac. A little shortcut I found is to open the `.cue` file with [Toast](http://www.macupdate.com/info.php/id/8719) as if you were going to burn it, which Toast can do, but choose File, Save As Disc Image instead. Toast will prompt you for the location to save the disc image, then dump the file there. Drop the resulting .toast file into Toast's Disc Image section and hit Mount, and the data from the disc image (and thus the original `.bin`/`.cue` image) will be mounted on your Mac without burning them to a CD or DVD first. It's a bit of a long way around, but it works, and might save you a CD-R.
