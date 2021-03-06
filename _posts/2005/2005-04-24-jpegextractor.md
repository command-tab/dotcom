---
layout: post
title: jpegextractor
---
I recently found a cool little open source Java program called "jpegextractor" which looks for JPEG images inside of other files, regardless of their type.  It can accomplish this because JPEG files have a short but distinct beginning and end marker.  Jpegextractor runs through a given file looking for occurrences these two blocks, and if found, copies the data between them to new JPEG image files on your disk.

One purpose I've found for it is extracting the artwork from purchased iTunes songs via the command line, as the cover art is stored as JPEG data inside the MPEG-4 protected file (however, only the audio is encrypted, not the cover image).  It is possible to copy the artwork out via iTunes song info window, which I found out later.

Using jpegextractor isn't hard at all.  With it downloaded, `cd</span> to the jpegextractor folder, and then do `java jpegextractor /path/to/file.m4p`, replacing /path/to/file.m4p with whatever file you want to juice for JPEG images.  If anything is found, it will dump out an "output0.jpg", or more, numbered sequentially.

    $ cd ~/Desktop/jpegextractor/ 
    $ java jpegextractor Ready to Rise.m4p
    Ready to Rise.m4p
     =&gt;output0.jpg (519887 bytes)
    Extracted 1 JPEG file(s) with 519887 bytes from 1 input file(s).

[jpegextractor homepage](http://schmidt.devlib.org/software/jpeg-extractor.html)
