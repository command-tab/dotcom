---
layout: post
title: DVD Backup Software
---
Macworld published a great [comparison of DVD copying software](http://www.macworld.com/2005/03/reviews/dvdcopy/index.php?lsrc=mwrss-0305) for the Mac, detailing the two major competitors, Roxio's [Popcorn](http://www.roxio.com/en/products/popcorn/index.jhtml) ($50) and [DVD2OneX](http://www.dvd2one.com/) ($65).  While I find that both programs work well, I disagree slightly with their buying advice.

It should be noted here as well, that neither of these programs can directly backup commercial DVDs because of the CSS encryption and Macrovision encoding used to protect the discs.

Popcorn has it's ease-of-use advantages, particularly in that it has fewer steps than DVX2OneX.  One of the drawbacks of this, as with just about anything that makes complex processes easier, is that you sacrifice some control.  And when it comes to encoding video, I like to have total control.  When you compress and burn a full DVD with Popcorn, you don't have the option of disabling certain audio tracks with other languages.  Normally this wouldn't be a problem, but since you are limited to about 4.4 GB of usable space on a DVD±R, any space used for extras like foreign audio take valuable (and sometimes very noticeable) quality away from the video.  However, both Popcorn and DVD2OneX have the option of removing language tracks if you choose to compress the main movie title only.

Before writing this, I was under the impression that there was no way to preview a movie compressed with Popcorn before it was burned to disc.  After tinkering with Popcorn a little, I discovered that once you've entered all your settings, you can choose File, Save as Disc Image, and your video will be compressed and written to a .toast image.  You can then open that image and preview it with DVD Player as if you inserted the finished disc.  This is one "feature" I thought previously available only with DVD2OneX, as it produces just a `VIDEO_TS` folder that can also be played with DVD Player by choosing File, Open `VIDEO_TS` Folder.

DVD2OneX offers the ability to define the size of your output, which I sometimes need to do because the usable space on DVD±R discs varies just a little.  You could also compress a movie to fit on a mini DVD disc if you so desired.  DVD2OneX has several different encoding methods, although I don't notice a whole lot of difference between them.  With [mkisofs](http://fink.sourceforge.net/pdb/package.php/mkisofs) installed, you can also create a disc image, but I find that this time is better spent previewing and burning the `VIDEO_TS` folder with DVD Player and Toast, respectively.

The number one advantage of DVD2OneX, is speed.  As the MacWorld article noted, DVD2OneX is significantly faster than Popcorn -- 19 minutes faster for the title they encoded.  Since both applications need to compress data and burn it, you should be able to spend those extra minutes burning your compressed movie.

Popcorn is still at version 1.0, and will likely jump up in speed with future releases.  Until then, I prefer DVD2OneX.
