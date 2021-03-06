---
layout: post
title: Magstripe Snooping
---
Here's a little mid-week hardware hack: building a magstripe card reader (a.k.a. credit card reader).  When completed, the device can pull data off just about any type of common magstripe card, including credit cards and identification tags.

Last summer I took a trip to Ohio and made it a point to visit a gigantic store in Dayton -- [Mendelson's Liquidation Outlet](http://www.meci.com). They carry just about everything you could want, however I was particularly interested in the several floors of electronics surplus items. I happened across a magstripe reader with a connector attached, but it was unwrapped with no documentation. It's surplus, so you take what you can get. On the off-chance it might be useful for a project such as this, I paid about $10 for it. It's been kicking around since then, and only recently have I done something with it.

I looked up the documentation for the reader I had using a model number found on the bottom, and discovered it was an Omron 3S4YR-HSR4. It could read common cards and output TTL signals, so I searched around some more to see what could be done with it. I found a SourceForge project dedicated to magstripe readers, called [Stripe Snoop](http://stripesnoop.sourceforge.net). They provide [diagrams](http://stripesnoop.sourceforge.net/hardware/reader.html) showing how to connect the reader to a PC game port, so I took a trip to my local RadioShack for a matching connector. With a little soldering, I had the finished magstripe reader ready to go.

The Strip Snoop project also maintains an open source program for reading and parsing the card data that is sent in from the reader unit.  With my aging Windows box fired up (ugh), I swiped nearly every magstrip card I could find to see what they contained.  For example, I was surprised to find that my college student ID contained only my social security number as an identifier.

In short, building a simple magstripe reader isn't too hard a task, and it's interesting to see what information is hiding from you even when it's right in the palm of your hand. While the reader I built only connects to a PC game port, the signals are standard TTL level, so building a USB version is quite feasible. With complete software and diagrams available from the [Stripe Snoop](http://stripesnoop.sourceforge.net) project, it's trivial to get a basic reader up and running on affordable hardware. Total project cost was about $12 plus a few minutes of soldering.

**Update:** Via [Bruce Schneier](http://www.schneier.com): [Ownership of Mag Stripe Readers May be Illegal](http://www.schneier.com/blog/archives/2005/11/ownership_of_ma.html) in Illinois. Crazy.
