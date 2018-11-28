---
comments: true
date: '2007-10-03 16:53:45'
layout: post
title: 'Hacking Verizon: Free Mobile Web on the LG VX 8600'
categories: [Hacking, Technology]
---

Any Verizon customer can tell you the company mantra: if the customer wants it, make them pay for it. Verizon's mobile web is no exception: by disallowing the user to change certain settings on the LG VX8600 phone, they effectively force him to use Verizon's mobile web service, or none at all. Long story short: users cannot take advantage of free WAP services (such as that of Google) because Verizon wants you to pay to use theirs.

However, by making a minor firmware update, you can enable your phone to use free WAP providers, giving you full access to the mobile web without paying Verizon a dime (aside from airtime minutes, of course). Here's how I did it.<!--more-->

## What You'll Need

You'll need a few things:

* Windows OS (This is surely doable on Mac/Linux, but I don't discuss how)

* VX 8600 USB cable (available from Verizon's "music pack" or individually on eBay)

* [BitPim](http://www.bitpim.org) (I used version 1.0.1)

* Drivers ([These](http://robby-blog.s3.amazonaws.com/2007/hacking-verizon-free-mobile-web-on-the-lg-vx-8600/lgusbmodemdriver_whql_eng_ver_481.exe) should work; [this software](http://www.vzam.net/vcastmusic/step3.aspx?file=VZMM2-DL-LG-Bld39-81k-83k-85k-8550-86k-87k-94k-98k-99k-002.exe) contains the official drivers)

* Hex Editor (I use [UEStudio](http://www.ultraedit.com/), but you can use whatever you like; however do _not_ use a text editor--doing so will render your phone useless!).

## What to do

1. Install the drivers. You can do this by installing either of the executable files described as "drivers" linked in the above section.

1. Connect your LG VX8600 to your computer.

1. Install and open BitPim. Configure it to use your "LGE CDMA USB Serial Port (COMX)" where X is your COM port. If you need more info on this, consult [www.bitpim.org](http://www.bitpim.org).

1. In BitPim, go to the "View" menu and select "View Filesystem."

1. Download the file /OWS/paramtable1.fil. My copy was 1863 bytes. If yours is a different size, I strongly suggest that you leave it alone.

1. Open paramtable1.fil in a hex editor of your choice and move to byte 3. It should be a '00'. Change it to '20'. Save it. For copyright reasons, I cannot post mine; you need to do this step yourself.

1. Overwrite the paramtable1.fil file on your phone with the one that you just edited.

1. Exit BitPim and disconnect your phone from your computer.

1. Restart your phone.

1. Go to the main menu on your phone.

1. Press "0" [zero].

1. When prompted for a size digit service code, enter 000000.

1. Press 8. This should bring you to the "WAP Setting" menu.

1. Press 1 to manage your proxy address.

1. Press 1 to change the primary address.

1. Remove the existing text and enter "wap.google.com"

1. Press "OK" to save your change.

1. Press "CLR" to go back to the "WAP Settin" menu.

1. Press 2 to manage your proxy port.

1. Press 1 to change the primary proxy port.

1. It probably says "80." Change it to "8080."

1. Press "OK" to save your change.

1. Press "END" to exit the service menu.

1. Restart your phone.

## Using the Free Mobile Web

Turn on your phone and press the up arrow! Voila!
