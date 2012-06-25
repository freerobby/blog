---
comments: true
date: '2009-09-05 17:30:29'
layout: post
title: Use Time Machine with Wake on LAN to Enable Network Backups to Sleeping Devices
categories: [Hacking]
---

**Update Sept 6, 2009: **I've created a project at github to simplify this process. More details [here](https://github.com/freerobby/wakemachine).

**Task**: You want to use Time Machine wirelessly to backup your Mac to a drive on another Mac on your network.

**Problem**: If the target machine is in "sleep" mode, your backup will fail.

**Solution**: Send a "magic packet" to the target machine to wake it up if it's sleeping.<!--more-->

**Gotcha**: New Macs [support WOL via Airport](http://www.tuaw.com/2009/08/29/snow-leopard-extends-wake-on-lan-feature-if-your-config-is-ri/). However if you're using an older Mac, the target machine must be connected via ethernet (the machine you're backing up can still be connected via wifi).

Let's roll:

## Prep the Target Machine

The target machine is the Mac that will _hold_ your backups.

1. On the target machine, go to System Preferences and open the "Energy Saver" panel.

1. Configure sleep settings as desired

1. Be sure to check the "Wake for Ethernet network access" box at the bottom.

1. Close out of system preferences.

1. Open System Profiler from your Utilities directory in Applications.

1. Click  "Network" in the left panel.

1. Click "Ethernet" in the top panel.

1. In the bottom panel, scroll down until you see "Ethernet:" with a line under it showing something like "MAC Address 00:15:d4:a3:cf:1b". Write down this 12-digit MAC address.

1. Exit System Profiler

## Configure the Host Machine

The host machine is the Mac that you will be backing up.

1. On the host machine, [install MacPorts](http://www.macports.org/install.php) if you haven't already.

1. Open up a Terminal from your Utilities directory in Applications.

1. Type: "sudo port install wakeonlan" and press return.

1. Enter your password when prompted, and wait while MacPorts installs the utility and its dependencies.

1. Open Automator in Applications.

1. Create a new "Application" workflow when prompted.

1. Double-click the "Run Shell Script" library item on the left. In the box that appears, erase "cat" and instead type:
    
       macaddress="00:00:00:00:00:00"
       while true
       do
    	   results=`syslog -k Sender com.apple.backupd -k Time gt -10s -k Message Seq 'Starting standard backup'`
    	   if [ -n "$results" ]
    	   then
    		   /opt/local/bin/wakeonlan "$macaddress"
    		   while [ -n "$results" ]
    		   do
    			   sleep 10
    			   results=`syslog -k Sender com.apple.backupd -k Time gt -10s -k Message Seq 'Starting standard backup'`
    		   done
    	   fi
    	   sleep 10
       done

1. In the first line, replace the 00:00:00:00:00:00 with the MAC Address that you wrote down earlier. Be sure to keep the quotes.

1. Choose File > Save As..., and name it "WOL Daemon" in the Applications folder when prompted.

1. Exit Automator.

1. Go to System Preferences and open the "Accounts" panel.

1. Click "Login Items" at the top.

1. Click the + icon to add a new one.

1. Select the WOL Daemon that you just created, and check the box next to it marked "Hide".

1. Restart your computer, and voilà, your target machine will now be woken up if it's asleep while Time Machine runs.