---
layout: post
title: Invert iTunes Music Store Links
---

This tip has been around since Apple introduced links to the iTunes Music Store from your own music library (version 4.5?), but I always find the need to do it on any new OS X install.  Normally, clicking the grey iTunes link arrow takes you to the iTunes Music Store right from your music library, but I hardly ever want to do that.  Luckily, someone at Apple thought of this too, and included a hidden setting that lets you browse your own music library using those links.  To change the behavior from linking to the Music Store to linking to your own library, quit iTunes and enter the following in the Terminal:

    defaults write com.apple.iTunes invertStoreLinks -bool YES</code>

Upon relaunching iTunes, clicking the grey arrows will now narrow your music library to the selection you made, as opposed to whisking you off the the Music Store. If you ever need to search the Music Store using those arrows, hold down the Option key to temporarily change the behavior back. Read more about this hint on [macosxhints.com](http://www.macosxhints.com/article.php?story=20040429122915489&query=invert).

(For iTunes under Windows, hold Control to invert behavior.  I'm not sure how to make the change "stick" on Windows, though...)
