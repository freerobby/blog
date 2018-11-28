---
comments: true
date: '2008-10-24 10:31:08'
layout: post
title: Keep Your Play Counts and Statistics When Moving Your iTunes Library
categories: [Hacking]
---

If you're an iTunes user who doesn't let iTunes manage your music collection, you'll find that iTunes isn't very cooperative when it comes to moving your music around. For example, if you decide you want to move your music from your internal drive to an external drive, you'll find that you have to re-import your music, costing you all of your playcounts, playlists and library statistics.

There's a better, easier way.<!--more-->

Here's what this how-to guide assumes:

1. You're a Mac user.

1. You want to move your music from one location to another.

1. The directory structure in which your music resides will not change, but rather you will be moving all of it under some top-level folder.

1. You want to keep your iTunes library as it currently exists.

Here's how to do it:

1. Quit iTunes

1. Make note of the top-level directory under which your music currently resides. For example, since I am moving my music from my user's Music folder, my directory is "/Users/robby/Music".

1. Move your music from your old location to your new location.

1. Make note of the new top-level directory under which you've put your music. For example, since I moved my music to an external hard drive called "Music", my new directory is "/Volumes/Music".

1. Open up Finder and navigate to your "iTunes" directory (by default, this is in your user's "Music" directory).

1. You should see a file called "iTunes Music Library.xml". Open it up with your favorite text editor.

1. Open said text editor's find/replace dialog.

1. In the "Find" field, type "file://localhost/<old directory name here>"

1. In the "Replace field, type "file://localhost/<new directory name here>"

1. Select "Replace All".

1. Save the file to disk.

1. Go back to the Finder box. Drag the file named "iTunes Library" to your desktop. If you see files named "iTunes Library Extras.itdb" and "iTunes Library Genius.itdb", do the same with those files.

1. Open iTunes. (Don't panic, your library should be empty).

1. Select File > Library > Import Playlist...

1. Select the iTunes Music Library.xml file that you edited and click Open.

1. iTunes will import your library with your new folder locations.

1. The import will create duplicates of the iTunes default playlists, so you may want to delete those copies.

1. If all goes well, you can delete the iTunes Library files from your desktop.
