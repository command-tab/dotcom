---
layout: post
title: 'Boot Camp: Last Resort'
---
In my endless tinkering with my computer set-up, I ran into my second major issue with Boot Camp, and managed to find a working solution worth documenting. Starting with a single Mac OS X Leopard volume, Boot Camp Assistant kept failing and reporting "not enough space left on device" while attempting to live-partition my hard drive into two partitions for OS X and Windows (newer versions of Mac OS X can partition hard drives while booted, without any formatting). However, I had over 50% of the drive's capacity free, so there should have been lots of space left on the drive. Clearly something was amiss...

Having started out with computers as a relatively old school Mac user -- one who had to backup and erase a hard drive to partition it -- I was immediately suspicious of the new-ish live-partition tool. To work around that, I tried booting the Leopard DVD and running Disk Utility from the Utilities menu, then partitioning the drive using that method. Again, I was met failure, but with an ambiguous "partition error" on which Disk Utility did not elaborate. The "Verify Disk" command reported that my volume was in good shape, despite my suspicions of corruption. DiskWarrior 4 also confirmed that the volume's directory structure was intact. With 90+ GB free on my MacBook Pro's 160 GB disk, how could I have "not enough space" to simply slice off a 20 GB Windows partition for run-of-the-mill use?

Out of quick-fix ideas, I decided to back up my Mac OS X volume, erase the drive, partition it, restore my OS X image to the big partition, then install Windows to the new smaller partition. Without a network-ready imaging utility like [Ghost](http://www.symantec.com/norton/ghost) or [TrueImage](http://www.acronis.com/homecomputing/products/trueimage/) for Mac OS X (are there any?), I had to do this a slightly more complicated way:

1. Boot Mac OS X and connect to a network share on another computer (a networked PC, in my case).
2. Run [SuperDuper!](http://www.shirt-pocket.com/SuperDuper/) and back up the entire contents of the drive to the other computer.
3. When done, boot the Leopard DVD and run Disk Utility again, and erase and partition the drive into one HFS+ Journaling partition for Mac OS X and one FAT32 partition for Windows.
4. Boot a Windows CD, and "quick format" the FAT32 partition to NTFS (since Disk Utility can't natively create an NTFS volume), then install Windows.
5. Install Boot Camp drivers from the Leopard DVD: The Windows volume on the Leopard DVD contains the necessary Boot Camp drivers. Nice touch, Apple!
6. Boot from the Leopard DVD again, but run Terminal this time -- there's no point-and-click way to connect to a network share from the DVD...
7. Typically, you'd do `mount_smbfs` to connect to a Windows share, but it failed with `mount_smbfs: failed to load the smb library: Unknown error: 1102" (No luck with mount -t smbfs, either)`. `mount_afp` appears to work, though.
8. With no way to use SMB to get at the imaged Mac OS X volume made earlier, I downloaded a trial version of [Extreme-Z IP](http://www.grouplogic.com/products/extremez-ip/?fa=free-trial), which provides AFP file and printer sharing support for Windows. After skipping prompts about Printer Sharing and automatically importing my SMB/Windows shares, it worked beautifully.
9. Back at the Terminal on the MacBook, `mkdir /Volumes/Sharename; mount_afp afp://username:password@192.168.1.10/Sharename /Volumes/Sharename` mounted Sharename from the PC onto /Volumes/Sharename on the Mac over Ethernet. (The hidden /Volumes/ folder is where all connected Mac volumes show up).
10. Back under Disk Utility, I was almost able to Restore the disk image to the proper volume over the network as if it were a local volume, but... it was grayed out in the file picker dialog.
11. The "Scan Image for Restore" button resulted in a failed process, but it DID add the disk image to the sidebar of Disk Utility, which enabled drag-and-drop such that I could restore it to the HFS+J volume.

After a few hours of restoring data, my MacBook Pro is back, with Mac OS X on one volume just as I left it right before the imaging, and a fresh Windows install on the other. Surely Apple never meant for Boot Camp to be this complicated, but they underestimated the extent of my tinkering and day-to-day use! I hope my documentation can help someone in a similar situation.

**Resources**

* [Apple Support Discussions - Full restore from a remote disk](http://discussions.apple.com/message.jspa?messageID=6042140)
* [AFP Third Party implementations](http://en.wikipedia.org/wiki/Apple_Filing_Protocol#Third-party_implementations)
