Shareutils
==========
Various utilities for sharing things you see on your screen with others.

* **clipboard2web**: Sends the text you have selected with your mouse to a paste
site, and puts the URL to the paste in your "middle-click" clipboard.
* **screenshot2web**: Lets you select a region of your screen with the mouse, then
sends a screenshot of that area to a paste site, giving you back the URL in
your clipboard.
* **video2web**: Lets you select a region of your screen with the mouse, then
records a screen capture of it. You guessed it - it also uploads to a paste
site and give you back the URL in your clipboard.

Set up
------
Once you've got the scripts, you'll want to make sure you have some
dependencies installed. The following debian/ubuntu packages will suffice:

* curl
* xclip
* imagemagick
* recordmydesktop
* python-xlib
* xautomation
* libnotify-bin

Here as a one-liner:

```
sudo apt-get install curl xclip imagemagick recordmydesktop python-xlib xautomation libnotify-bin
```

Using the scripts
-----------------
The best way is to have them all bound to keys for easy invocation, but
initially, it's best to run them directly just to check that they work.

**clipboard2web**

Select some text anywhere on your screen (terminal, browser, whatever). Then
run this script. If it has worked, you'll shortly see the text you selected
open in a browser, and if you middle-click, you'll find that the URL to view
the text has been put into your "middle click" clipboard.

The way I typically use this, is to select something I want a work colleague to
see (stack trace, for example), run this script (by pressing a key, more on
that later), then middle-clicking in IRC for them. We don't auto-paste the link
by default, as this gives a safety buffer, but you can rig that up if you want.

**screenshot2web**

Run the script. Your cursor should change to a crosshair. Drag to select an
area on the screen. If the script works, you'll shortly see a screenshot open
in a browser, and if you middle-click, you'll find that the URL to view the
screenshot has been put into your "middle click" clipboard.

Typical usage is as for clipboard2web. Note that as it's uploading an image,
there might be a short delay between you finishing selecting, and the image
being pasted.

**video2web**

Note that you need to run this script once to start recording, *and again to
stop and trigger the upload*. If you record too much, it's likely the upload
will take quite some time, and hog your bandwidth too!

The first time you run the script, the cursor *won't* change to a crosshair
(bug), but you'll be able to select a region of the screen. From then on, that
region will be recorded. Once you've done what you wanted, run the script
again. If it works, after a reasonable delay (transcoding/uploading the video),
it'll open in a browser and you'll find that the URL to view the video has been
put into your "middle click" clipboard.

Again, note that you need to run the script once to select the area and start
recording, and then again to stop the recording and do the transcode/upload.

**Binding the scripts to keys**

Once you know they all work, binding them to keys is the best way to get the
most advantage from them.

For the i3 window manager, I did this in my config file:

```
bindsym F6 exec ~/src/shareutils/clipboard2web
bindsym F7 exec ~/src/shareutils/screenshot2web
bindsym F8 exec ~/src/shareutils/video2web
```

If someone knows how to do it for gnome and wants to send me a pull request
adding those instructions here, please do!

If you have them bound to keys and they're not working, the file
$HOME/.xsession-errors is often where they'll be logging.

Legal
-----
Authored by Nigel McNie & Martyn Smith, Shoptime Software. All code placed in
the public domain.
