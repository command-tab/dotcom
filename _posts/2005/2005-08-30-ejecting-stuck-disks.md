---
layout: post
title: Ejecting Stuck Disks
---

Once in a while, the Finder will refuse to eject discs, claiming they're still "in use," even though you may have no programs or files open and accessing it.  I've tried quitting all open applications, closing all windows, and making sure no files were open (such as a disc image on the disc itself) -- nothing will convince the Finder that the disc not in use.  Then I ran across the Terminal command:

    hdiutil eject -force [volume]

where `[volume]` is the volume name or Unix device (i.e. `/dev/disk3`, attainable by doing `df` first).  After hitting Return, the drive pops open.

`hdiutil` is a great little tool Apple provides with OS X, and it can do many things besides eject stuck discs -- create and resize images, burn `.dmg` files, mount and unmount them, all from the command line using a very simple syntax.

And, for the record, my position on the disk/disc naming scheme is this: If it's magnetic media, it's "disk."  And if it's optical, it's "disc."  It doesn't really matter, but I make the distinction anyway.
