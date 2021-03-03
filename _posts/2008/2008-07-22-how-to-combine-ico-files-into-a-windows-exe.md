---
layout: post
title: How to Combine ICO Files into a Windows EXE
---
Lately I've been working with Mozilla's [XUL](http://www.mozilla.org/projects/xul/) platform under [xulrunner](http://developer.mozilla.org/en/docs/XULRunner), and found that I needed to make a properly branded Windows application, but had no tools or knowledge on how to "glue" standard .ico icon files together, or insert them into an already-compiled .exe file. After some research and a little trial and error, I found a method that works. Assuming you have some prepared 16, 24, 32, and 48 pixel images suitable for an icon set, here's how to go about getting them from Photoshop into a Windows application, using only free software.

**Photoshop to Multiple .ico Files**

The first step to branding a generic executable with your own icons is to get them out of the graphics program and into .ico format, which is the standard for Windows software icons and cursors. [IcoFormat](http://www.telegraphics.com.au/sw/#icoformat), a free Photoshop import/export plugin for handling .ico files, will easily handle the task. Once installed to your Photoshop plugins folder (and Photoshop subsequently restarted), you can save each of your icons as a .ico file using "Save As...", and choosing ICO from the Format menu in the resulting dialog. Repeat for each icon size you wish to embed (or, if you're ambitious, try recording a Photoshop action to automate the process).

**Multiple .ico Files to One .ico File**

To allow Windows to display the best size icon for the current folder view, it's best to combine the desired .ico files into a single file. The free [Icollator](http://www.the-vardemans.net/andrew/software/) program will take in multiple icons and produce a single .ico file ready for embedding. You may need the [Java Runtime Environment](http://www.java.com/en/download/manual.jsp) to run Icollator, if you don't already have it. Like Icollator, JRE is also free download.

**Embed the .ico File**

The last step is to embed the single .ico file (containing two or more icons) into the .exe. Launch the freeware [Resource Hacker](http://www.angusj.com/resourcehacker/) utility, and Open the target .exe. Then select Action -> "Add a new Resource...", and pick the combined .ico file you made in the previous step. Give the resource a simple name like "ICONS", and click Add Resource. Save the changes to the .exe, and switch to Windows Explorer. You'll notice that the .exe now has the embedded icon set, and Windows will show the correct size icon for the current view mode.

Also, you'll notice that Resource Hacker made a backup of the .exe before embedding, just for safe keeping. Also potentially of interest: [Getting application name and icon right with XULRunner](http://adblockplus.org/blog/getting-application-name-and-icon-right-with-xulrunner) from the AdBlock Plus blog
