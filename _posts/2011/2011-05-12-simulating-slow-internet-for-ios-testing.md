---
layout: post
title: Simulating Slow Internet for iOS Testing
---
Apple's iOS Simulator is an acceptable environment for testing development code, but when users purchase your finished app from the App Store, they'll be running it on real hardware, particularly on networks that are likely much less reliable than your home or office internet.

To ensure your app performs well under real-world conditions, you can load up the code on a device and go outside, but then you can't debug as easily. And even if you bring your MacBook Air with you, what if your Verizon iPhone is everything you hoped, and it performs admirably on the worst of days? To get around all of this, you can approximate an unreliable network with [SpeedLimit](http://mschrag.github.com). SpeedLimit is a System Preferences pane for intentionally and selectively slowing down specific ports and domains.

![speedlimit window](/assets/speedlimit.jpg)

Download and install SpeedLimit, add one or more hosts (separated by commas, as seen above), select a target speed, and click Slow Down. Subsequent network requests matching the criteria you set will be throttled, giving you time to go all out testing your app's performance and error handling. Does it crash when users hit the Back button while a UITableView is loading? Does it lock the UI while downloading avatars or thumbnails? SpeedLimit lets you find out, and be confident in your networking code.
