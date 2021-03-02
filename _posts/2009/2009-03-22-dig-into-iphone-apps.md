---
layout: post
title: Dig into iPhone Apps
---
So you're curious about the contents of iPhone and iPod Touch apps, including artwork, sounds, and more? Here's how to dig into an application and see what goodies are hidden inside. Standard copyrights still apply.

**Sync Your Apps with iTunes**

Assuming you already have the target application on your iPhone or iPod Touch (just "iPhone" from this point forward for brevity's sake), simply sync your iPhone with your Mac or PC. Doing so will backup your device and transfer any purchased applications in both directions. With the target application now on your computer, navigate to your iTunes "Mobile Applications" folder, where iTunes typically does its own file housekeeping. Under Mac OS X, the default location is `/Users/yourname/Music/iTunes/Mobile Applications/`.

**Unzip an App**

Copy your target `.ipa`-suffixed application to a different location, ensuring that the original stays in the Mobile Applications folder to keep iTunes happy. To get inside the application, rename its extension to `.zip`. Open the zip file, and you will have access to the guts of the app (except the source code, of course).

**High-res App Artwork**

Directly inside the unzipped application folder, you'll find a file named `iTunesArtwork`, with no extension. A hex editor revealed that the file is typically a jpeg image, so rename it to include `.jpg` at the end, and you'll end up with the same 512x512 pixel artwork displayed by iTunes when browsing downloaded Applications. To get at other resources, open up the adjacent "Payload" folder, and you'll find a `.app` file -- the application bundle that runs on the iPhone. Right- or Control-click on the `.app`, and choose "Show Package Contents" to open up the bundle.

**Sounds**

Sounds are typically found among the many resources directly inside the application as files with extensions like `.caf`, `.mp3`, `.aif`, and `.m4a`. At this point, the organizational structure is up to the application's developer, so you may need to look around a little. Leopard's QuickLook feature is a boon in times like this, helping assess a file's purpose without opening half a dozen applications.

**Other Graphics**

Also nestled inside iPhone applications are many of the graphics used throughout the app. It's possible that some may be drawn by code, but complex graphics are generally stored as images. However, viewing the images isn't as easy as renaming the files as before. This will be a bit trickier, as the iPhone works some magic on the images before finishing the app build process, leaving images in an iPhone-optimized state. Fortunately, the process can be reversed with a little bit of Terminal trickery:

1. Copy all `.png` images to a new folder elsewhere. Images of other formats (`.jpg`, `.gif`, etc.) should be readily viewable.
2. Download David Watanabe's [modified iPhonePNG](http://www.newsfirex.com/blog/?p=176) command-line application, unzip the archive, and open up Terminal from your /Applications/Utilities folder.
3. Type `cd `, then drop the iPhonePNG folder into the Terminal, and tap Return to switch to that folder.
4. Type `./iPhonePNG `, drop the folder of encoded images into the Terminal, and tap Return to decode the whole folder full of images.
5. The output folder sites beside iPhonePNG, so type `open .` and tap Return (open space dot) to open the current folder (a dot, in Unix terms) in the Finder. Open the decoded images folder and have a look around!
