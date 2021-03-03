---
layout: post
title: 'fmTuner: A Last.fm Plugin for WordPress'
---
fmTuner is a WordPress plugin for retrieving song details from your [Last.fm](http://www.last.fm) profile and publishing them anywhere in your WordPress theme. It provides options for choosing among your Recent, Loved, or Top tracks, as well as tools to adjust the update frequency and appearance.

Of particular note is the customizable Display Format option. Using simple tags like `[::artist::]` and `[::image::]` intermixed with regular HTML, you can tweak your Last.fm tracks exactly how you like, or however your WordPress theme requires. You have full control!

**Download**

[Download the latest fmTuner from WordPress.org](http://wordpress.org/extend/plugins/fmtuner/)

**Requirements**

* WordPress 2.7 or newer.
* PHP 5 or newer
* Basic knowledge of PHP, HTML, and WordPress.

**Installation**

* Upload fmtuner.php to a directory inside `/wp-content/plugins/` directory. For example: `/wp-content/plugins/fmtuner/fmtuner.php`
* Ensure `/wp-content/plugins/fmtuner/` is writable by your webserver.
* Activate the plugin through the "Plugins" menu in WordPress.
* Set up options in the "Settings" menu in WordPress.
* Place the PHP code `if(function_exists('fmtuner')) { fmtuner(); }` in your templates, to call up fmTuner.

**Release History**

* **fmTuner 1.1** Released on Feb. 1, 2010 Added a placeholder image field to the fmTuner Settings page, which will be substituted when tracks have no artwork. Tested under WordPress 2.9.1.
* **fmTuner 1.0.8** Released on Nov. 3, 2009 Fixed a bug with the `[::url::]` fmTuner tag that caused Last.fm links to appear incorrectly.
* **fmTuner 1.0.7** Released on Apr. 23, 2009 Tracks with foreign character sets now display more accurately.
* **fmTuner 1.0.6** Released on Mar. 29, 2009 You can now display more than 10 Recent Tracks, and you should get fewer tracks without artwork.
* **fmTuner 1.0.5** Released on Mar. 22, 2009 Track information is now properly escaped to handle $ signs, quotes, and other non-alphanumeric characters.
* **fmTuner 1.0.4** Released on Dec. 14, 2008 Made minor tweaks for fmTuner Settings page under WordPress 2.7.
* **fmTuner 1.0.3** Released on Nov. 15, 2008 By request, a `[::number::]` fmTuner tag has been added, which emits a sequential number for each track (starting at 1). This is particularly useful for CSS and JavaScript display purposes.
* **fmTuner 1.0.2** Released on Oct. 5, 2008 Added a cURL-based alternative to `file_get_contents` to hopefully resolve "URL file-access is disabled" issues. If `allow_url_fopen` is disabled in the php.ini, cURL will be used to fetch the Last.fm feed instead.
* **fmTuner 1.0.1** Released on Sept. 9, 2008 Added better failure checking and informational messages, removed development code, and updated instructions.
* **fmTuner 1.0** Released on Sept. 6, 2008 Initial release.
