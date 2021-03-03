---
layout: post
title: How to Import and Export ICNS with Photoshop
---
If you're interested in making replacement icons for Mac OS X applications, the Leopard Developer Tools received an updated version of the Icon Composer utility, which combines multiple PNG images into one ICNS file. Once exported, the combined file is suitable for use inside an application bundle, by choosing Show Package Contents from the Finder's action menu (or a right-click) and browsing to `Contents/Resources/` and replacing the appropriate ICNS file (make sure to rename your icon to match the existing one!).

To run the process the other way, first find the desired ICNS file inside the application, and open it with the built-in Preview application. Preview understands the transparency inherent to ICNS icons, and allows you to save the file as a PNG, ready to open and work on in Photoshop!

**Update:** After looking around on MacUpdate for something simple, I found [img2icns](http://www.shinyfrog.net/en/software/img2icns/), a freeware drag-and-drop icon converter that can turn a PNG image into a folder icon. With it, you can Get Info for the converted folder icon and copy and paste it onto another application or document. It's the perfect little icon utility to go with this minimalist workflow, and it's Leopard-ready!
