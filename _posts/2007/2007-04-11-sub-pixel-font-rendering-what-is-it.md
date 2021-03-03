---
layout: post
title: 'Sub-Pixel Font Rendering: What is It?'
---
For the past few years I'd heard the term "sub-pixel rendering" in various font and graphics related writings, and wasn't really sure what the fuss was about. I finally read up on the technology and was surprised to find what a difference it makes in display clarity. The crux of sub-pixel rendering is using the three red, green, and blue elements that make up a single pixel to effectively triple the horizontal resolution of an LCD display. More resolution in the same physical space lets you show more data, and thus render more clearly. Wikipedia's definition left much to be desired, however Steve Gibson has an [outstanding page](http://www.grc.com/ctwhat.htm) -- and freeware utility -- clearly explaining the subject.

Knowing how sub-pixel rendering works, it's easy to see how it could also be applied to graphics and gaming. Where an edge is computed, the resulting line could be shown more accurately (as far as the human eye is concerned) by rendering with respect to the sub-pixel elements of the display. Of course, the technology doesn't work nearly as well on CRT displays, but for LCDs, it appears to provide ultra-crisp images and text. I wonder if Apple plans to make use of this awesome technology in the next revision of Mac OS X, or perhaps on the iPod and iPhone displays.
