---
comments: true
date: '2007-10-11 17:31:30'
layout: post
title: Get Gmail Email on Your Palm TX
categories: [Hacking, Technology]
---

I was disappointed when Google released [a mobile Gmail client for PalmOS 5](http://www.google.com/mobile/mail/index.html), but did not provide support for Palm TX devices. The TX, after all, is Wi-Fi- and Bluetooth-enabled, and thus an ideal candidate for any mobile application that takes advantage of wireless internet.

It turns out that getting Google's Gmail client up and running on the Palm TX is both quick and easy.<!--more-->

![GMail PalmOS Photo](http://robby-blog.s3.amazonaws.com/2007/get-gmail-email-on-your-palm-tx/1011071600.jpg)

Before you get started, you'll need two things:

1. The IBM WebSphere Everyplace Micro Environment (IWEME) [ [Available Here](http://www.palm.com/us/support/jvm/download.html) ]

1. The Gmail application for PalmOS 5 [ [Direct Download](http://www.freerobby.com/wp-content/uploads/gmail.prc) ]

Begin by installing the IWEME. Palm provides the following instructions, for Windows and Mac, respectively. **This Environment MUST be installed onto the Palm in RAM and NOT on an external SD card**.

Windows Installation Instructions:

1. Download [JVM.zip](http://palmone.r3h.net/downloads.palmone.com/JVM.zip) (1.77MB ZIP File)

1. [Extract the contents](http://kb.palmone.com/SRVS/CGI-BIN/WEBCGI.EXE?New,Kb=PalmSupportKB,ts=Palm_External2001,case=obj%2826436%29) of the zip file using a standard unzip utility.  Note the location where the folder **PALMOS JVM 5.7.2** is unzipped to.

1. Launch Palm Desktop. Select **Quick Install** icon.

1. Select the correct user name from the User list.

1. Navigate to the **PALMOS JVM 5.7.2** folder that was unzipped in Step 2.

1. In that folder, open the **JVM** folder.

1. In that folder, open the **ARM4T** folder.

1. In that folder, select **J9JavaVMMidp20.prc** and **JavaVMCheck_enUS.prc**.

1. If you want a non-English version, you must install these files:
    - J9JavaVMMidp20.prc file
    - J9JavaVMMidp20_xx.prc file with your language version ("de" is German, "es" is Spanish, "fr" is French, "it" is Italian, "ja" and "jp" are Japanese, "zh" and "CN" are Chinese)
    - JavaVMCheck_xxXX.prc file with your local version

1. Drag and drop the selected files to the Quick Install window.

1. Depending on your setup and requirements, you can explore the other folders and install the other files. The ones listed above are mandatory; the others are optional. Consult the Java software developer for more information about which files you need to run the application on your device.

1. Perform a HotSync operation.

Macintosh Installation Instructions:

1. Download [JVM.sit](http://palmone.r3h.net/downloads.palmone.com/JVM.sit) (1.68MB SIT File)

1. Your web browser should automatically expand the file and you will see a folder named **PALMOS JVM 5.7.2** on the desktop (or in your default download folder). If your web browser does not expand the file automatically, you will need to use an [expanding utility](http://kb.palmone.com/SRVS/CGI-BIN/WEBCGI.EXE?New,Kb=PalmSupportKB,ts=Palm_External2001,case=obj%2826436%29) (such as Aladdin Stuffit Expander) in order to decode the .sit file. Note the folder location.

1. On your Mac, launch Palm Desktop.

1. From the HotSync Menu select Install Handheld Files.

1. Select your user name from the drop down menu.

1. Navigate to the **PALMOS JVM 5.7.2** folder that was unzipped in Step 2.

1. In that folder, open the **JVM** folder.

1. In that folder, open the **ARM4T** folder.

1. In that folder, select **J9JavaVMMidp20.prc** and **JavaVMCheck_enUS.prc**.

1. If you want a non-English version, you must install these files:
    - J9JavaVMMidp20.prc file
    - J9JavaVMMidp20_xx.prc file with your language version ("de" is German, "es" is Spanish, "fr" is French, "it" is Italian, "ja" and "jp" are Japanese, "zh" and "CN" are Chinese)
    - JavaVMCheck_xxXX.prc file with your local version

1. Drag and drop the selected files to the Install Handheld Files window.

1. Depending on your setup and requirements, you can explore the other folders and install the other files. The ones listed above are mandatory; the others are optional. Consult the Java software developer for more information about which files you need to run the application on your device.

1. Perform a HotSync operation.

Once you've installed the IWEME, install the Gmail app (gmail.prc) like any other PalmOS app--using Quick Install feature or other method of your choice. I recommend installing this application to RAM for speed and efficiency reasons associated with the Java VM/runtime; however it should be able to run directly from an SD card.

Now, connect your Palm to the internet. You can do this however you normally do--via Wi-Fi or Bluetooth.

Lastly, launch your newly-installed Gmail app, enter your login credentials, and check your email!

Thanks to Dennis McCunney for helping me locate the original .prc file.
