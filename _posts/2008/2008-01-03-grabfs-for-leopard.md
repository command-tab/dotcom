---
layout: post
title: GrabFS for Leopard
---
[Mac OS X Internals](http://osxbook.com/) author Amit Singh has put together a unique plugin for [MacFUSE](https://osxfuse.github.io/) called [GrabFS](http://osxbook.com/book/bonus/chapter11/grabfs/), which is a virtual file system of running applications, in which you can navigate through windows and view current screenshots. That's a lot going on in one sentence, so lets take it bit-by-bit:

MacFUSE is a Google project headed by Amit to port the [FUSE](https://github.com/libfuse/libfuse) tool from Linux to Mac. Effectively, it mounts what appears to be a disk image, but the contents of the image can be from any source. The key to FUSE is that the apparent files and folders can be conjured up based on information obtained elsewhere, be it from other files and folders, a remote server, Flickr image streams, or process lists. Plugins allow authors to devise new ways of presenting a hierarchy to the end user, regardless of the original data format.

In the case of GrabFS, it lists each running application on your Mac as a folder inside the virtual FUSE disk. Inside every folder is a screenshot TIFF file for each window of that application, which you can view in place or copy out for later use.

MacFUSE isn't a new project, but talented developers are continually thinking up new sources of information to plug right into your desktop.
