---
comments: true
date: '2009-09-01 14:23:23'
layout: post
title: Installing MySQL via MacPorts on Snow Leopard for Ruby Development
categories: [Hacking, Technology]
---

There are a number of tutorials floating around that explain how to install MySQL 5 on Snow Leopard. They all recommend the x86_64 universal binary supplied by MySQL. If you'd like to install MySQL via MacPorts (MySQL5 is [certified compatible](http://trac.macports.org/wiki/snc/snowleopard)!), here are the steps:<!--more-->

First, install MySQL with developer libraries:

    sudo port install mysql5-devel

Then create the required databases:

    sudo /opt/local/lib/mysql5/bin/mysql_install_db --user=mysql

If you get permissions errors, run (warning: don't do this in production!):

    sudo chmod -Rf 777 /opt/local/var/db/mysql5

and repeat.
	
Now set your mysql password:

    /opt/local/lib/mysql5/bin/mysqladmin -u mysql password 'your-password-here'

Install the MySQL gem:

    sudo gem install mysql -- --with-mysql-config=/opt/local/bin/mysql_config5

or, if you want to use version 2.7 (instead of the latest 2.8.1):

    sudo gem install mysql --version 2.7 -- --with-mysql-config=/opt/local/bin/mysql_config5

You're ready to roll. To start your MySQL daemon, run:

    sudo /opt/local/lib/mysql5/bin/mysqld_safe &
