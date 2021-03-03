---
layout: post
title: PHP5 and MySQL 5 on Leopard
---
A few quick notes about building MySQL 5.x and getting it working under Leopard:

* Follow Dan Benjamin's excellent [MySQL on Leopard tutorial](http://hivelogic.com/narrative/articles/installing-mysql-on-mac-os-x).
* Copy the PHP configuration example to the actual expected location: `sudo cp /etc/php.ini.default /etc/php.ini`
* Edit it, and add `/private/tmp/mysql.sock` to both mysql.default\_socket and mysqli.default\_socket.
* Save, and restart Apache: sudo apachectl graceful

Once completed, the default PHP5 setup that comes with Mac OS X 10.5.x will be able to communicate with the MySQL version built using the above linked tutorial. Time to get developing!
