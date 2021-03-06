---
layout: post
title: 'Mac Meet Xbox: Part 2'
---
Welcome to Part 2 of my multi-part introduction to setting up a Xbox-based home media center in a Mac environment. So far, the Mac has been absent, but the Xbox hardware must first be set up to communicate on your home network. This section will cover opening the Xbox, installing the modchip, and loading the necessary firmware.

**Cracking the Case**

To begin modding, you'll have to open your Xbox. _This will void your warranty._ If you send your Xbox to Microsoft for repair after tampering with it, they will refuse to work on it. However, if you have even basic computer hardware skills, then there's no reason to be alarmed -- there is a great [Xbox modding community](http://forums.xbox-scene.com/) that has developed and will gladly help you out of a jam. I can't say enough about the importance of like-minded individuals who can help you through impossibly complex situations involving small wires, config files, and unsupported hacks. Like everything technological, Xbox modding is an involved topic, but there's plenty of help available.

I should note that I'm aware of "softmod" solutions that do not require a modchip, but I've found that installing a modchip is the safest and most feature-packed path to choose, especially if you haven't done anything like this before. In the past, I've killed a few Xboxes with a bad flash, and resurrecting them took more time, effort, and research than most would be willing to invest. The Xecuter 2.6 CE Lite chip I recommended in [Part 1](/2006/08/18/mac-meet-xbox-part-1/) sports a number of features to help you avoid this situation, and protect both your Xbox and your modchip from being turned into paperweights.

Screwdriver in hand, it's time to get to the heart of the matter by cracking the case and dissecting the system. As the Xbox is quite similar to a PC, disassembly should be an easy task if you've ever taken apart a computer. The case is held together by six T-20 Torx screws which hold the top and bottom plastic shells together. Peeling back the feet and stickers on the underside will allow access to the screws, as they're concealed from initial observation. If you prefer, you can avoid leaving a thin veneer of stickiness by simply poking your screwdriver through the stickers instead of peeling them off. With the screws out, the top case can be lifted off the bulk of the components. Three smaller T-10 screws hold down the 8 or 10 GB hard drive and DVD-ROM. After unplugging the power and IDE cabling from both drives, lift them straight out to expose the motherboard. Eleven more T-10 screws fasten the motherboard to the chassis. Remove them all, including the ones beside the A/V connector, and gently lift out the motherboard. If it gets stuck towards the back (as it often does), lift the front first, while keeping controller port wires out of the way. You can then set the case and power supply assembly aside and focus on the motherboard.

**Xbox Versions**

Because of the changes made in various revisions of Xboxes, it's necessary to categorize the Xboxes into groups which are modded using the same procedures. The earlier Xboxes are version 1.0 through 1.5, and the newest is 1.6. The latest version requires the "patch" circuit mentioned above, as well as an alternate source of power (which is readily available all over the motherboard). If you're following along, you can easily check which version you have just by taking a look at the video encoder chip on the motherboard, right next to the A/V output. If you find that the chip has "Xcalibur" with an Xbox logo stenciled on the surface, your Xbox is a 1.6 and requires the additional circuit.

**Installing the Modchip**

The installation procedure for the Xecuter 2.6 CE chip is nearly identical to that of the more expensive Xecuter 3 chip, so I'll provide the [installation instructions](/assets/x3_ce_v10_v16.pdf) here. However, you can stop reading at page 16, as the rest doesn't apply to the 2.6 CE. Team Xectuer does a great job of detailing all the intricacies of installing the chip, so be sure to double-check your work. With care, you can even install the front panel switches without cutting into the case.

Installing the modchip will probably be the most tedious part of the project, so be sure to take your time on this step.

**Choosing a BIOS**

Now that your modchip is installed and working, it's time to choose the code that will allow you to run non-Microsoft software, which includes our target program: Xbox Media Center. This isn't a terribly important decision, as it will be nearly invisible. However, you will want to look for a few key features: Enabling use of hard drives greater than 137 GB, and the ability to stop the Xbox from resetting upon ejecting. My personal favorite BIOS (and there are dozens to choose from) is the Xecuter 2 build 5035, as it reads all important settings from a config file stored on your hard drive, whereas other BIOSes require you to patch the code and reload them onto your chip.

Unfortunately, this and other Xbox BIOS software isn't technically legal. Most are modified versions of the official Microsoft BIOS, which, no matter how small, are still copyrighted. Modification and distribution of copyrighted code is illegal, but progress often doesn't stop in the name of law. The Xecuter 2 5035 BIOS can be found all around the internet. It's usually distributed in [RAR](http://en.wikipedia.org/wiki/RAR) format, so you'll need either [UnRarX](http://www.unrarx.com/) or [MacParDeluxe](http://www.xs4all.nl/~gp/MacPAR_deLuxe/) to extract the contents (Windows users can use the free [7-zip](http://www.7-zip.org/)).

**Booting and BIOS Flashing**

When you first power on your newly modded Xbox, you'll hopefully be greeted with the FlashBIOS screen. If your Xbox fails to boot properly, perhaps flashing alternating red and green lights, have a second look at the modchip installation instructions and make sure you followed each step for your version Xbox (taking careful note of the `D0` point on your motherboard). If all went well, FlashBIOS' blue screen will be displayed, and you're now ready to load the non-Microsoft firmware onto your modchip. The easiest way to accomplish this is via the chip's network flashing capabilities.

The absolute easiest way to flash the BIOS over the network is using a simple home router, nearly all of which assign IP addresses to any attached device. Connect your Xbox to your router using a length of straight-through Ethernet cable, your Mac via Ethernet or AirPort, and choose Enable Network Flashing from the FlashBIOS menu onscreen. FlashBIOS will bring up the Xbox's networking hardware and provide you with an IP address to which you should direct your web browser. On the page that loads, you can choose a BIOS file to upload, which will then be flashed. In my case, I chose the X2 5035 `.bin` file and uploaded it to the Xbox. It's worth noting my much [earlier post](/2005/11/18/xbox-bios-tips-for-mac/) about slicing and combining BIOS files on the Mac -- the Xecuter 2.6 has two 1 MB banks, so you may need to double-over the BIOS to completely fill the bank adjacent to FlashBIOS. After FlashBIOS has written the file to the chip, flick the Bank Select switch on the front panel board, and reboot from the new BIOS. If it worked, you'll be greeted with "Xecuter Rox My Box" under the Xbox logo. Your Xbox will appear to boot up like normal, or so it seems...

This concludes the second, and undoubtedly most complicated edition of "Mac Meet Xbox." In the next installation, we'll be covering installtion and formatting of a new hard drive, and laying the foundation for Xbox Media Center.

**Resources**

[Modding a v1.6 Xbox in 10 Minutes](http://www.techfreaks.org/articles/modxbox.shtml) (softmod) [Xbox-Scene Forums](http://forums.xbox-scene.com)

**Mac Meet Xbox: Navigation**

Part 1: [Why Xbox + Choosing Chips](/2006/08/18/mac-meet-xbox-part-1/)

Part 2: [Cracking the Case + Installing and Flashing](/2006/09/08/mac-meet-xbox-part-2/)

Part 3: [Installing XBMC](/2006/12/21/mac-meet-xbox-part-3/)

Part 3.1: [Networking in Detail](/2007/02/10/mac-meet-xbox-part-3-point-1/)
