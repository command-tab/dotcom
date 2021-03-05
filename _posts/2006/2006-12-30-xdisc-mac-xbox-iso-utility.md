---
layout: post
title: 'Xdisc: Mac Xbox ISO Utility'
---
Often when dealing with Xbox content on the Mac, it's useful to be able to create a bootable DVD, perhaps of a game or Xbox Dashboard program.  While Xbox Media Center doesn't run well from a DVD, games, utilities, and other programs are designed to be playable from a disc.

The Xbox can't normally read computer formatted CDs like ISO 9660 and Joliet (XBMC can, though), but to make a bootable disc, it must be of the proper format.  Microsoft designed a custom disc format for the Xbox in an attempt to stop piracy and secure the system, however it was quickly reverse engineered to allow for all kinds of uses.  Xdisc is an Xbox disc image creator/extractor for Mac OS X, built on top of the open-source [extract-xiso](https://github.com/XboxDev/extract-xiso) utility, which can be compiled for most operating systems.  It can build an Xbox ISO file (disc image) from a folder on your computer, or can directly FTP into the Xbox and create an image of a folder or DVD, including games.  It can also extract the contents of an Xbox ISO, producing the original files that make up the software.  FTP is fully integrated into extract-xiso -- and thus Xdisc -- making for a great solution that can communicate directly with the Xbox to get the job done.

The author, known as "trackfive," does not have a personal site that I can find and link to, so I'm hosting a copy of Xdisc 1.01 [right here](/assets/Xdisc.zip), so you can download away.  Also included in the download are several drag-and-drop applets to quickly create and extract XISOs without launching the application and messing with settings.

**1/7/2007 Update:** Trackfive has also produced some [Automator plugins](/assets/Xdisc_Automators.zip), which allow you to Control-click (right-click) on a folder or file and create or extract the Xbox ISO in one simple step.  What could be easier?
