---
layout: post
title: MacBook Pro Insomnia
---
For the past several weeks, my MacBook Pro had been occasionally waking up during periods where it was expected to be in sleep mode. Even with the lid closed, it would briefly wake up, illuminate the screen and Apple logo, then fall back asleep moments later. Seemingly random, it would sometimes happen only once every other day, and other times it would happen sequentially with only seconds in between cycles. I had no idea if the issue was hardware or software, but it didn't seem major enough to warrant an AppleCare call.

A quick trip to the Console application in the Applications > Utilities folder reported dozens of instances of "USB caused wake event (EHCI)", which gave me some initial Google hits. The obvious answer is that a USB device was waking up the computer, however I rarely had USB hardware plugged in when the random awakenings were occurring.

As it turns out, [others](http://tancredi.co.uk/2007/12/9/solving-macbook-wake-from-sleep-issue) [have](http://forums.macrumors.com/archive/index.php/t-428248.html) had this problem before. As indicated in the previous links, Mac OS X keeps its power schedule inside /Library/Preferences/SystemConfiguration/com.apple.AutoWake.plist, but this file didn't exist for me, apparently "confusing" Mac OS X. Without it, it would exhibit the symptoms I was encountering.

Following suggestions, I opened System Preferences, Energy Saver, Schedule, where you can schedule system sleeps and wakes. By toggling on a scheduled wake, clicking OK, then disabling it, the com.apple.AutoWake.plist was re-created, and left with no scheduled sleeps or wakes. So far, this has cured my MacBook Pro's insomnia!
