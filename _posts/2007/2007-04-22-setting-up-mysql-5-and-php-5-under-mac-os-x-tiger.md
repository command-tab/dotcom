---
layout: post
title: Setting up MySQL 5 and PHP 5 under Mac OS X (Tiger)
---
While setting up MySQL 5 and PHP 5 today, I documented the steps I took to get it all running under Tiger.  Here's the basic rundown if you'd like to move to these new versions as well.

**Downloads**

* Developer Tools -- Xcode 2.4.1 from [Apple Developer Connection](http://developer.apple.com)
* MySQL 5.1.17 -- mysql-5.1.17-beta-osx10.4-powerpc.dmg from [mysql.com](http://dev.mysql.com/downloads/mysql/5.1.html#macosx-dmg)
* PHP 5.1.2 -- source code from [php.net](http://www.php.net)

**Install Xcode**

Installation of Apple's Xcode Developer Tools is straightforward -- just install the .pkg file inside the .dmg if you downloaded it, or run the .pkg from the discs that came with your computer.

**Install MySQL 5**

Setting up MySQL is just as easy as installing Xcode, as the developers have kindly put together a .pkg installer.  You could always compile it yourself if you have the need.  Also included in the .dmg are a StartupItem and Preference Pane, both of which I find handy (although StartupItems are a bit out-of-date, and should probably be replaced with a launchd item).

**Install PHP 5**

Unpack PHP's .tar.gz file with your favorite [decompression utility](/2006/09/18/the-unarchiver/), and open a Terminal window.  Type `cd`, followed by a space, then drop the uncompressed php-5.2.1 folder right into the Terminal window and hit Return to change directory to the PHP files.

Type `./configure --with-mysql=/usr/local/mysql --with-apxs=/usr/sbin/apxs` to configure the PHP installation, noting the location where MySQL keeps its files (so PHP knows how to get to it in the future).

While PHP is configuring, in a new Terminal window, you should set the root password for MySQL.
Enter `cd /usr/local/mysql/bin`, then `./mysqladmin -u root password 'new-password'`, where new-password is your chosen MySQL root password.  Note that this has nothing to do with your computer's "root" password, and is entirely separate.

Back at the PHP prompt, you'll see "Thank you for using PHP." when it's done configuring.  You can then enter `make` to compile PHP from the source code.  This may take a while.

When done, enter `sudo make install` to install the files to their predetermined locations.

**Reconfigure Apache**

You're almost done, except that the Apache web server doesn't know to handle .php files for PHP 5.  PHP 4 comes preinstalled with Mac OS X, but PHP 5 changes your Apache config file to enable itself (to include its shared objects when Apache boots), which turns off PHP 4.  In this state, .php files will be printed out to the web browser as text files instead of executed -- that's not good!  You'll have to tweak the config file and reboot Apache to make it all go again.  If you have the [TextMate](http://macromates.com) command-line utility `mate` installed, these next steps are quite easy.

Enter `sudo mate /etc/httpd/httpd.conf` (or `sudo pico /etc/httpd/httpd.conf` without TextMate) in the Terminal to edit the Apache config file.  Find `&lt;ifmodule mod_php4.c&gt;` and change that 4 to a 5, as we're now using `mod_php5.c`.

You'll also want Apache to recognize `index.php` as a Directory Index file, so hunt down `DirectoryIndex index.html` and add a space, then `index.php` to the list, so it looks like `DirectoryIndex index.html index.php` when done.

At this point you can save and exit if you prefer, but I like to make one last change so I don't have to dig to /Library/WebServer/Documents every time I want to edit a file I'm working on.  In the root of your hard drive, create a folder called WebServer, and then jump back to TextMate (or the Terminal window) where you're editing the Apache config file.  Find the line `DocumentRoot "/Library/WebServer/Documents"` and change it to `DocumentRoot "/WebServer"`.  After making this change, also change the location a few lines down: `&lt;directory "/Library/WebServer/Documents"&gt;` to `&lt;directory "/WebServer"&gt;`.  Finally, save and exit.

Back at the Terminal prompt, enter `sudo apachectl graceful` to reboot Apache and let everything fly.  I hope that helps some people setting up a PHP coding environment out there!  A final note: watch out for the "smart quotes" Wordpress likes to insert -- they may cause copy-and-pastes to produce failures in the Apache config file.
