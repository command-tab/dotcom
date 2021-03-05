---
layout: post
title: iTunes Podcast Auto-Subscribe
---
A few days ago, [Jon Maddox](http://www.jonsthoughtsoneverything.com "Jon's Thoughts On Everything") and I found the need to make iTunes to subscribe to a podcast with one click from Safari. After a few guessing attempts and some meager Googling, we were unable to come up with a solution. Today, I ran across a tutorial on how to do just that. The `pcast://` prefix, instead of `http://` will make the Mac version of iTunes open and subscribe to the podcast URL immediately following the prefix. For the Windows side of things, there are several more steps which involve the creation of an XML file linking to the podcast. With a little server-side user-agent switching or some other per-client trickery, it should be relatively simple to produce a Mac or Windows "one click subscribe" link. Check out the full details at [Podcast Shuffle](http://www.podcastshuffle.com/2005/07/one-click-subscribe-itunes.html).
