---
comments: true
date: '2009-09-06 13:15:17'
layout: post
title: Wake Machine
categories: [Hacking]
---

Wake Machine enables Time Machine to backup to a target that is sleeping. Without Wake Machine, such backups will fail because the remote disk won't mount.<!--more-->

Wake Machine runs as a mock daemon on the client. When Time Machine initiates a backup, Wake Machine sends a [magic packet](http://en.wikipedia.org/wiki/Wake-on-LAN#Magic_packet) to the target machine to wake it up if it's sleeping.

Caveats: If you're using an older Mac, the target machine must be connected via ethernet (the machine you're backing up can still be connected wirelessly via Airport). New Macs support wake on LAN using Airport.

## Prerequisites

Wake Machine works out of the box with OS X Leopard and Snow Leopard.

However, you'll need [git](http://git-scm.com/download) in order to install Wake Machine.

## Getting Started

Installation is as easy as cloning the Wake Machine repository. Navigate to the directory you'd like to install it in and run:
    
    git clone http://github.com/freerobby/wakemachine.git

Once installed, you must set up Wake Machine. The recommended method for doing this is the following:

1. Ensure that both the target computer is awake.

1. Run a time machine backup.

1. Run Wake Machine setup:
 
       bash wakemachine.sh setup

Setup will automatically detect your time machine target, resolve its IP address and discover its MAC address. This information will be written to your user profile.

## Running Wake Machine

To launch the Wake Machine daemon manually, run:
    
    bash wakemachine.sh &

To set up Wake Machine to run automatically on your system:

1. Go to System Preferences and open the "Accounts" panel.

1. Click "Login Items" at the top.

1. Click the + icon to add a new login item.

1. Select the wakemachine_daemon executable, and check the box next to it marked "Hide".

1. Restart your computer

Voilà, your target machine will now be woken up whenever Time Machine runs.

## Key Links

* [Wake Machine development at github](http://github.com/freerobby/wakemachine/tree/master)

* [Wake Machine tracking at Pivotal Tracker](http://www.pivotaltracker.com/projects/28564)

## Acknowledgments

Wake Machine uses the [Wakeonlan perl script](http://gsd.di.uminho.pt/jpo/software/wakeonlan/) written by Ico Doornekamp and José Pedro Oliveira.