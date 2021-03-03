---
layout: post
title: Consolas Cursor Fix
---
If you've attempted to use Consolas as your choice programming font on the Mac, you may have noticed ([as I did](/2008/02/19/finding-the-perfect-programming-font/)) an odd issue with the font, where your blinking cursor hangs much lower than the current line. Oddly enough, this little issue only seems to affect Mac OS X. Even the Consolas set that ships with Microsoft Office 2008 has the same problem! Yet, when the same exact font file is used under Windows, the cursor position is correct.

John Gruber [mentioned](http://daringfireball.net/linked/2008/12/15/bbedit-91 "Daring Fireball: BBEdit 9.1") that [BBEdit 9.1](http://www.barebones.com/products/bbedit/demo.html) now ships with Consolas as its default font, so I decided to see if it had the same cursor problem I had experienced in the past. As it turns out, BBEdit's version of Consolas works just fine, as seen in the image above. However, it doesn't include the other styles like Consolas Bold, Italic, and Bold Italic.

Through one way or another, the copy of Consolas that ships with BBEdit 9.1 is different than the one that ships with Microsoft Office 2008. To make system-wide use of the working version, [download BBEdit 9.1](http://www.barebones.com/products/bbedit/demo.html), mount and open the .dmg, and navigate to:

(Control-click BBEdit, and choose "Show Package Contents" to get inside the application bundle): `BBEdit.app/Contents/Resources/Fonts/consola.ttf`

Copy consola.ttf from BBEdit's "Fonts" folder to your own Fonts folder at /Users/you/Library/Fonts, or /Library/Fonts if you want to make it available to everyone who has an account on your computer. Then, fire up your favorite editor, set Consolas as your preferred fixed-width font, and get coding!

**Update:** Bare Bones has apparently changed the version of Consolas that ships with BBEdit versions later than 9.1, and they now have the cursor problem as well...
