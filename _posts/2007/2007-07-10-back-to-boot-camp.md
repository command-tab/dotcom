---
layout: post
title: Back to Boot Camp
---
After getting used to working with Boot Camp on my new Intel Mac, I decided to borrow the second partition for a few days to dual boot two copies of Mac OS X (which worked flawlessly, by the way).  Once I was done, I assumed I could pop in my Windows disc and do a clean format-and-install over the second Mac OS X partition.  Boy, was I wrong.

Windows Setup displayed only one "partition" as it saw things -- the entire 160 GB drive.  Not wanting to blow away my entire main Mac OS X installation, I was unsure of how to get back to using Boot Camp normally.  Launching Apple's Boot Camp Assistant utility presented me with unhelpful messages such as "The startup disk must be formatted as a single Mac OS Extended (Journaled) volume or already partitioned by BCA for installing Windows" and "This startup disk is not supported."  What to do?

One fact I was sure of was that I did indeed have two real partitions on my hard drive.  Disk Utility clearly showed two partitions under my single drive hardware device.  Both partitions were formatted as Mac OS Extended Journalled (HFS+J) volumes, but Windows refused to see them as individual partitions, perhaps because it only comprehends the Microsoft-standard FAT32 and NTFS formats.  Hoping to fix the matter, I used the `diskutil` command line tool to format the second partitions as "MS-DOS FAT32", even though the Disk Utility point-and-click interface only offered HFS+ and HFS+J in its Format menu.  `diskutil` noted that, because I was booted off the drive, the resulting partition would not be bootable.

`diskutil`'s note about bootable volumes gave me an idea -- boot from the Mac OS X Installation DVD and see what tools are available there.  Upon booting the DVD that shipped with my machine and choosing English as my main lanugage, I found the Utilities menu at the top of the Installer.  In there was a launchable copy of Disk Utility -- the very same tool found in your `/Applications/Utilities` folder.  It listed many more formats under the Erase tab for the second Boot Camp partition, and I happily formatted it as "MS-DOS", knowing it would leave me with one HFS+J partition and one FAT32 partition.  Erase and format was successful, so I rebooted and held down Option to force the OS selection screen to appear.  [At this point I checked and found that, yes, Boot Camp Assistant will rediscover your partition and prompt you with the usual options.  It must simply check for the existence of a FAT32 or NTFS volume to run properly.]  I discovered moments later that it's possible eject and insert disks while at this screen, so I popped in my Windows XP CD and let Setup begin once more.  This time, Setup listed the following partitions:

    E: Partition1 [Unknown] 200 MB (EFI)
    F: Partition2 [Unknown] 133120 MB (Note: this is the main Mac partition)
    Unpartitioned space 128 MB
    C: Partition3 (WINDOWS) [FAT32] 19052 MB
    Unpartitioned space 126 MB

The C: FAT32 formatted partition was approximately the correct size, so I figured it had to be the correct choice.  FAT32 can be limiting in file size, but Windows was able to easily re-format the partition to NTFS on the spot (Quick format is <em>much</em> faster than a full format).  After babysitting the Windows installer for the next 30 to 40 minutes, everything was working again in Boot Camp land.  Holding Option at startup is back to presenting the usual Macintosh HD and Windows operating systems, and booting into Windows is fast as it ever was.
