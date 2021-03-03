---
layout: post
title: How to Test RAM Under Mac OS X
---
Whenever I get a new stick of RAM for my Mac or PC, I'm always eager to just plug it in and start using it to its fullest, but having worked on hundreds of computers and encountering dozens of bad memory modules has convinced me that thorough testing is a must. While off-the-shelf PCs can run a copy of the free [Ultimate Boot CD](http://www.ultimatebootcd.com) tool to perform RAM tests, Macs are a little bit more complicated in this respect. If you've purchased AppleCare for your Mac, it comes with a bootable [TechTool Deluxe](http://www.micromat.com/index.php?option=com_content&task=view&id=37&Itemid=51) disc, but you're otherwise left to your own devices when it comes to hardware tests.

Fortunately, with a little preparation right now, you can boot your Mac into [Single User Mode](http://docs.info.apple.com/article.html?path=Mac/10.4/en/mh343.html) and do a complete RAM test in the future. While you can run the necessary software in a fully-booted system, I recommend doing testing in Single User Mode where there are far less programs loaded in memory, and less chance of an important system component getting corrupted if your machine freezes or [kernel panics](http://docs.info.apple.com/article.html?artnum=106227) -- common symptoms of bad memory. A modified Mac OS X boot CD would be ideal, but that's another post for another day!

**Download Memtest**

The testing setup isn't terribly complex; I've taken the liberty of putting together an [installable package](/assets/memtest_422.zip) which will put the Memtest utility into your /usr/bin/ folder. Memtest is a Unix command-line program that does the memory testing, and is the Mac equivalent of [MemTest86](http://www.memtest86.com/download.html).

**Memtest Usage**

To run memtest on a new memory module, first shut down your computer and install the new chip. (Some helpful guides for doing this can be found at [iFixit](http://www.ifixit.com/Guide/Mac/), if you're unsure of the exact steps.) Ensure the chip is firmly in place, close up your machine (or don't, if you're a pessimist), and power it on while holding down the Command and S keys to force Mac OS X to boot into Single User Mode. Once you see a black screen with white text, you can release the key combination. After all the system logging is done scrolling past, type memtest all 2 to test all memory two times. Two passes should be enough to detect any blatant problems, but I wouldn't hesitate to let it run for hours on end if I suspected an intermittent memory problem (memtest all). When complete, you should be greeted with "All tests passed" if your new RAM is in good condition. If your system locks up or freezes indefinitely during the test, you may have a bad memory module on your hands.

**Feb. 16 2012 Update:** Memtest is still working under Mac OS X 10.7 Lion.

**Oct. 25 2012 Update:** Memtest is still working under OS X 10.8 Mountain Lion.
