---
layout: post
title: ThinkPad 1802 Error Fix
---
Of all the laptops I've worked on, IBM ThinkPads are by far the easiest to disassemble and fix. They're also pretty tough machines, as they survive substantially more damage than most of the Dell laptops I've seen. If I were a full time Windows user (and I'm not, despite the recent number of PC related posts), I would probably consider purchasing a ThinkPad. If it weren't for one tiny problem... Most newer ThinkPad models have a Mini-PCI slot and antennae, ready to be equipped with a standard wireless card. Mini-PCI may be unfamiliar to Mac users reading this blog, just as it was to me several months ago. Think of Mini-PCI as an AirPort Extreme connector, but standardized such that any manufacturer can create a compatible communications card. While the slot is standardized, IBM insists on crippling it via software to only accept "IBM brand" wireless cards -- which are really just OEM cards made by Philips and others. Upon booting a machine with a non-IBM card installed, the following POST error will be displayed:

>1802: Unauthorized network card is plugged in
>Power off and remove the miniPCI network card.

What a sneaky way to lock people into buying an expensive wireless card, when others can be bought for much much lower prices. (I suppose I can't complain, though, as AirPort Extreme is even more proprietary. Although, I've never had the need to use a different wireless card in my PowerBook -- I just bought the "whole widget" from Apple and that was that.) Luckily for ThinkPad owners, there exists a small fix for this "1802" error: a DOS program which will flip a single bit in the CMOS and allow use of any Mini-PCI wireless card. The program, no-1802.com by Tisheng Chen, can be found [here](http://jcnp.pku.edu.cn/~shadow/1802/). To make running this program easier for myself and others, I've prepared a bootable CD ISO and floppy disk image.

* [Download the CD ISO](/static/no-1802-cd.zip)
* [Download the Floppy Image](/static/no-1802-disk.zip)

Both files will require unzipping before use (use the free [7-Zip](http://www.7-zip.org/) or WinZip). Once unzipped, the CD version can be burned with Disk Utility or [Toast](http://www.roxio.com/en/products/toast/index.jhtml) on the Mac, or [ImgBurn](http://www.imgburn.com/) or Nero on the PC. The floppy disk version can be written with [Floppy Image](/static/floppyimage152.zip) for Windows, or `dd if=no1802.img of=/dev/fd0` in a Unix environment. The floppy image is a bit-for-bit copy of what I actually had on disk, and the CD version boots and loads the very same floppy into RAM, using a highly customized [Ultimate Boot CD](http://www.ultimatebootcd.com/). Hopefully this will allow ThinkPad owners to use any wireless cards, and not just those offered by IBM.

**5/17/06 Update:** I'm glad to see that people are having success with my pre-made wireless card fix. A list of some of the models affected by IBM's decision can be found [here](http://www.srcf.ucam.org/~mjg59/thinkpad/wireless.html), thanks to Matthew Garrett. He also has few pages with useful technical details on this topic, as well.

**8/30/06 Update:** For future reference: IBM "high rate" wireless+56K modem combo cards with FRUs 12P3637, 12P3863, 26P8472 and 91P7661 require separate modem drivers (that aren't part of the "high rate" package). The cards are made by Actiontec, but the the modem portion is made by Agere/Lucent, and the drivers can be found in IBM's list of downloads for the R32.

**9/10/06 Update:** This page was linked to at [ThinkWiki](http://thinkwiki.org/wiki/Problem_with_unauthorized_MiniPCI_network_card), where you'll find even more information on the 1802 error.

**Confirmed Working**

* A31, A31 2652-Q3U, A31 2652-1U6
* A31p, A31p 2653-CU5, A31p 2653-R3U
* G40 2384-EHU
* R40 2682-HU2, R40 2682-K2G, R40 2681, R40 2896-GZU
* R50 1830-48G
* R50e 1834-BZG
* R51
* T30, T30 2637
* T40, T40 2373, T40 2373-8CU, T40 2373-94G, T40 2374-GG2, T40 2374-DG1
* T41, T41 2374-7JG
* T42, T42 2373-BX9
* T42p
* X24
* X30
* X31, X31 2672-U31
* X40

**Confirmed _Not_ Working**

* R32
* R60
* T60
* Z60t
* X41 2525-6NH
* Lenovo x100e
* Lenovo x120e
