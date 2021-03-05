---
layout: post
title: 'Mac Meet Xbox: Part 3'
---
Welcome back to the "Mac meet Xbox" series, Part 3, where we finally get to the good stuff.  With the Xbox opened, modded, and ready to run beautiful, open-source, and decidedly non-Microsoft software, we're going to format and install Xbox Media Center.

**Getting XBMC**

Yet again we run into the issue of legality in the Mac meet Xbox series, as Xbox Media Center is compiled from source code using Microsoft's XDK (Xbox Development Kit).  The XDK is a series of Windows programs, drivers, and Xbox software which allows developers to write and debug software for the Xbox.  It is supposed to be available only to game publishers, however copies of it have leaked out onto the internet.  The source code for Xbox Media Center is freely available and open source, but when you compile it into an Xbox program (an .xbe file, akin to Windows' .exe files), you're using copyrighted software, thus the resulting executable contains a portion of copyrighted code.  Distributing such a copyrighted work violates the DMCA in the U.S., however laws in your country may vary.  For the sake of this tutorial, I'll leave the legalities up to you, but you should be aware of why the Microsoft XDK is publicly considered "off limits" in most discussion areas.  For more details, you can visit the [XBMC wiki](http://xboxmediacenter.com/wiki/index.php?title=Microsoft_Xbox_SDK) page regarding the XDK and its involvement with Xbox Media Center.

Building Xbox Media Center from source code with the XDK isn't a great option, let alone an easy one.  Thankfully, a few charitable people build and post copies of XBMC around the net.  I'll have to leave you to your own devices to obtain a copy.  As of this writing, the latest version is 2.0.1, and it can be found on popular sites.  Like the BIOS files mentioned in the previous Mac meet Xbox part, XBMC is also distributed in RAR format, which must first be decompressed.

**Dashboard Swap**

With a shiny new build of XBMC on your computer, you'll need to prepare the Xbox to receive the files.  The community that has developed around Xbox modding decided upon one of the best choices for file transfer -- FTP.  We're going to run an FTP server on the newly modded Xbox, browse through it's carefully arranged system files, and replace a bunch of them with Xbox Media Center.  First, though, you'll need an FTP server.

In the early days of Xbox modding, a replacement for Microsoft's Xbox "dashboard" was created, EvolutionX, and it served a number of needs: launching programs, flashing the Xbox's onboard BIOS, changing settings, and running an FTP server.  While others have since been developed, and even our very own Xbox Media Center is capable, we need something simple and easy to get off the ground.  The easiest way to run an FTP server is to boot a prepared EvolutionX disc, which automatically starts the FTP service.  Again, you can find discs to do the job all over the web.  Burn the disc image to a DVD-R, DVD+RW, or CD-RW, which are three of the most compatible disc types -- CD-Rs tend not to work well.  Pop in the disc, reboot your Xbox, and marvel at the first non-Microsoft application running on your Xbox.  By the time you see the spinning "EvolutionX" text, it's ready to accept FTP connections at the IP address displayed in the Utilities menu (assuming your network setup is the same as in [Part 2](/2006/09/08/mac-meet-xbox-2/)).

There are several Mac FTP programs that will work for the next task, however I strongly recommend Panic's [Transmit](http://www.panic.com/transmit/) client, which has proven to work reliably with the built-in FTP servers of the Xbox programs we'll be dealing with.  Launch Transmit, and connect to the IP given by EvolutionX, with the universal Xbox FTP login:

Username: `xbox`

Password: `xbox`

Of all your passwords, this should be the easiest to remember.

When connected, you'll be presented with a list of folders much like that of a Windows "My Computer" view: C:, D:, E:, and a few other drive letters.  Not surprisingly, the folders correspond to similarly arranged devices -- C: is for the main Xbox system files, D: is the DVD-ROM drive, E: is for extra files like game saves.  If you're curious, you can browse the contents of the optical drive by peeking inside D:, however the real guts of the Xbox's system lie in the C: folder.  Unlike Windows, however, the Xbox system files are stores right inside C:.  Opening it will list a number of important files, but the one to note is `xboxdash.xbe`.  This file, along with its associated fonts, sounds, and textures is the heart the Xbox software.  It's the green screen you're used to browsing through when you have no game inserted in the console or are about to play a DVD movie.  At this point, I would advise backing up all the contents of the C: drive to a safe folder on your computer, should you need them in the future.  Go "up" a directory where you can see the drive list again, and simply drag C: to your Mac, and wait for it to copy over.  (If you're so inclined, you might also drag over E: to back up your saved games and other data.)

Once the contents of C: are backed up and safely tucked away, promptly delete everything in the C: folder.  That's right.  Blow it away.  Doing so will rid your Xbox of its Microsoft dashboard and prepare the space for XBMC.  Short of re-copying the files you just backed up, you won't be able to get back to the standard Xbox dashboard any longer.  If you're going to make this machine a media center Xbox, you might as well go all the way and make the media center the default system.  With that, highlight everything in C:, and click Transmit's "Delete" toolbar button.

Some moments later, your C: folder will be empty, ready to accept new software.  At this point, _if_ you were to reboot your Xbox without the EvolutionX disc inserted, you would receive an error stating that your Xbox needs serious repair by trained Microsoft professionals.  Slim chance of that happening.  Browse to the contents of the decompressed Xbox Media Center folder and find `default.xbe` contained within.  Upload this file and all of its sibling files and folders, ensuring that the `default.xbe` is directly inside the C: drive.  This may take some time, as XBMC totals over 100 MB and has quite a few small files which can slow down the overall transfer.  Upon completion of the upload -- and this is important -- rename `default.xbe` to `xboxdash.xbe`.  You'll note that the original Microsoft dashboard had the same file name, thus we've replaced it with Xbox Media Center's main program.  Without an `xboxdash.xbe` to launch, the Xbox will produce an error screen.  Renaming Xbox Media Center's main program to match what the Xbox expects to find effectively tricks it into launching the new software at startup.

**The Final Test**

To ensure you've properly installed Xbox Media Center, open the DVD drive, remove the EvolutionX disc, and restart your Xbox.  If all goes well, you'll hear a startup tune and be greeted with the Xbox Media Center splash screen, and a brand new menu system.  Movies, music, pictures, programs -- it's all here.

If you've made it this far, consider yourself an official Xbox modder.  You've successfully opened the console, modified it to run non-Microsoft software, and installed your own replacement system.  Getting this far took countless hours of cracking and coding on the part of some very dedicated hackers, and you've managed to follow in their footsteps to assemble your own home media center.

**Mac Meet Xbox: Navigation**

Part 1: [Why Xbox + Choosing Chips](/2006/08/18/mac-meet-xbox-1/)

Part 2: [Cracking the Case + Installing and Flashing](/2006/09/08/mac-meet-xbox-2/)

Part 3: [Installing XBMC](/2006/12/21/mac-meet-xbox-part-3/)

Part 3.1: [Networking in Detail](/2007/02/10/mac-meet-xbox-part-3-point-1/)
