---
layout: post
title: A Tour of the AppleTV Insides
---
It never takes long for a dissection to take place after the release of a new Apple product, and the AppleTV is no exception. You knew it would happen soon enough, so here are a few details I noted when browsing through [the gallery](http://s22.photobucket.com/albums/b343/briantr/Apple%20TV/).

![appletv insides](/assets/appletv_inside.jpg)

For storage, the AppleTV uses a regular 2.5" SATA laptop hard drive, rather than the smaller 1.8" iPod hard drives. Laptop drives are plenty fast for most uses. Soon enough, a curious hacker will install a new hard drive and see just how much capacity the AppleTV can handle, as well as dicover what flavor of Mac OS X runs on the system. Linux will eventually be ported to the AppleTV, just because it can be. With all that onboard media processing hardware and network connectivity, the AppleTV has the potential to be more than just an iTunes livingroom extension, and I'm sure the hackers will be all over it in short order.

![appletv cpu](/assets/appletv_cpu.jpg)

This particular photo interested me, as it appears to be main processor on the AppleTV board. Not surprisingly, an Intel chip. However, it's not a stock CPU -- at least one not yet offered to the public. It's permanently soldered the the board, so there's little hope of a public release, as well as upgrading the AppleTV with a faster chip. The CPU's sSpec number, SL9YN (seen in the photo), as well as its diminutive size indicate it's probably a Core 2 Duo Mobile variant, operating at around 1.6 to 1.8 GHz -- perhaps a little slower if most of the heavy decoding is handled by the nVidia graphics chip. 

![appletv wifi card](/assets/appletv_wifi_card.jpg)

The AppleTV's WiFi connectivity centers around its tiny Broadcom wireless card, which can be found plugged into the onboard slot, next to the main power connector. It has two antennae attached, allowing it to reach even fringe AirPort base stations. The card itself is an _almost_-stock MiniPCI Express BCM94321MC WiFi card, offering 802.11a/b/g and draft-n wireless (but you knew it had 'n' already). It has Apple's signature engravings, but it's probably nothing more than a re-branded Broadcom device -- one less thing to engineer from the ground up is a good thing for already missed ship dates!

Overall, the AppleTV looks to be an adequately powerful machine for set-top uses, and is probably hackable in more ways than one. I can't wait to see what cool projects will make use of its internals in the near future!

For reference (thanks MacUser):

* [AppleTV Support](http://www.apple.com/support/appletv/)
* [TCP and UDP ports/protocols used by AppleTV](http://docs.info.apple.com/article.html?artnum=305115)
* [AppleTV starts up to a flashing question mark](http://docs.info.apple.com/article.html?artnum=305164)
* [AppleTV: How to run diagnostics](http://docs.info.apple.com/article.html?artnum=305190)

**Update:** Well, that didn't take long. Only 24 hours later, and some clever hackers have taken apart the AppleTV, plugged its hard drive into another machine via a USB adapter, and [modified the device to play XviD compressed video](http://digg.com/apple/XviD_fully_functional_on_Apple_TV). Apparently the AppleTV runs a stripped down version of Mac OS X 10.4.7, and uses standard QuickTime technologies to play back video, therefore current QT plugins easily add capabilities to the box. Once in, they also set up an SSH server and disabled the software firewall, for easy administrative access via a network. Zakalwe on the SomethingAwful Forums notes:

>The Xbox uses a 733MHz PIII. The 1Ghz Dothan (in the AppleTV) is a Pentium M which is a lot more beefy than a ~33% increase in clock speed would make you believe. The instruction set is a lot more efficient, the CPU has a pretty decent 2MB cache compared to ther Xbox's 128k and the FSB is up ~4 times faster.

Not only can you add in your own codecs like DivX and XviD, but with the help of [SuperDuper](http://www.shirt-pocket.com/SuperDuper/SuperDuperDescription.html), you can duplicate the hard drive's contents over to a new, [bigger drive](http://gizmodo.com/photogallery/appletv_120gig/1621990), and [add storage capacity](http://gizmodo.com/gadgets/home-entertainment/diy-apple-tv-hard-drive-upgraded-to-120gb-246567.php). Amazing stuff -- all within a day. What's next?

Keep your eyes on a new blog, [AppleTVHacker](http://www.appletvhacker.blogspot.com/), for up-to-the-minute news on hacks, mods, and upgrades.
