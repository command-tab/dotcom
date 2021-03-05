---
layout: post
title: WRT54G Won't Upgrade
---
After half an hour of messing around with my Linksys WRT54G v5 hardware, I was finally able to upgrade the firmware on the device.  I try to maintain a secure setup by using WPA encryption, HTTPS web-based management, and Ethernet-only administration.  However, it seems that all my conscientiousness worked against me when attempting to upgrade from v1.00.6 to 1.00.9.  For reasons known only to Linksys, you can't upgrade the firmware while logged in over HTTPS.  The kicker, though, is that you get no warning or indication that anything is malfunctioning -- the upgrade simply doesn't happen.  A text-based progress bar is displayed for about 3 minutes, and (about one in three times) you get the following error:

>Upgrade are failed.

The solution to this is to re-enable plain HTTP administration, log in unencrypted, and then retry the upgrade.
