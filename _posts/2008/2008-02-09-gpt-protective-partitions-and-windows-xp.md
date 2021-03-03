---
layout: post
title: GPT Protective Partitions and Windows XP
---
If you've formatted a bootable hard drive on an Intel Mac (or have perhaps been tinkering with the wholly unsupported [OSx86 project](http://www.osx86project.org)) and later decided to put the drive to use under Windows XP, you might find that you're unable to format the disk, with Windows Disk Management claiming the device is a "GPT Protective Partition." You can't format it, partition it, or even assign it drive letter. What gives?

The secret is that the GPT scheme protects itself from being read and possibly erased by utilities or operating systems which aren't able to correctly interpret it. Until just recently, I wasn't aware that a filesystem even had such a capability. I was under the false assumption that a utility running externally of the drive in question could always format a detected disk, no matter the filesystem in place. I doubt it could withstand the raw formatting power of [DBAN](http://dban.sourceforge.net), but it was enough to confuse Windows XP. How can the GPT scheme be undone? Typically, software that can create it can also destroy it. In my case, Leopard's Disk Utility application was able re-partition the drive as follows:

* Boot a Leopard DVD (retail or OSx86) and choose your native language at the first screen.
* Run "Disk Utility" from the "Utilities" menu and highlight the offending drive on the left.
* Navigate to the "Partition" tab, choose "1 Partition" from the Volume Scheme popup menu, select your new desired format (or "Free Space"), and make sure to click the "Options..." button
* From the "Options" screen, you can choose between GUID Partition Table, Apple Partition Map (for PowerPC Macs), and Master Boot Record. Choose MBR, and click OK.
* Click "Apply" to partition the drive using the more common MBR scheme, and thus completely erase all trace of the GPT partition.

Once the partitioning is complete, you'll be able to format and use the drive under Windows XP, Mac OS 9, or any other system incapable of comprehending GPT Partitions.
