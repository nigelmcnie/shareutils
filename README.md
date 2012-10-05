Various utilities for sharing things you see on your screen with others.

clipboard2web
-------------
Sends the text you have selected with your mouse to a paste site, and puts the
URL to the paste in your "middle-click" clipboard.

screenshot2web
--------------
Lets you select a region of your screen with the mouse, then sends a screenshot
of that area to a paste site, giving you back the URL in your clipboard.

video2web
---------
Lets you select a region of your screen with the mouse, then records a screen
capture of it. You guessed it - it also uploads to a paste site and give you
back the URL in your clipboard.

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

Then, run each script directly from the command line to see it in action and
make sure it works. Note that with video2web, the first time you run it, it'll
start recording, then you need to run it again to stop recording. This is
because we need to send a kill signal to recordmydesktop to make it stop.

Then, for maximum effect, bind the scripts to keys in your WM. For i3, I did
this in my config file:

bindsym F6 exec ~/src/shareutils/clipboard2web
bindsym F7 exec ~/src/shareutils/screenshot2web
bindsym F8 exec ~/src/shareutils/video2web

If you have them bound to keys and they're not working, the file
$HOME/.xsession-errors is often where they'll be logging.

Legal
-----
Authored by Nigel McNie & Martyn Smith, Shoptime Software. All code placed in
the public domain.
