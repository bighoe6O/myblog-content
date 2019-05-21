---
layout: post
title:  souris-logitech-m560
date:   2018-10-29 21:11:49 +0100
category: Système
tags: [Matériel]
---

<https://support.logitech.com/en_us/product/wireless-mouse-m560/specs>

<https://askubuntu.com/questions/255890/how-can-i-adjust-the-mouse-scroll-speed#360045>

	xinput list
	xinput list-props 12


	sudo apt-get install xserver-xorg-input-synaptics

now go to /usr/share/X11/xorg.conf.d and just edit the file 70-synaptics.conf


	cd /usr/share/X11/xorg.conf.d
	sudo nano 70-synaptics.conf

find the section Section "InputClass" Identifier "touchpad catchall" then add these options:

	Option "VertScrollDelta" "16"
	Option "HorizScrollDelta" "16"

The default number is 26 the lower the number it is faster to scroll, the higher it is slower to scroll. Finally it should look like this:

```
Section "InputClass"
        Identifier "touchpad catchall"
        Driver "synaptics"
        MatchIsTouchpad "on"
# This option is recommend on all Linux systems using evdev, but cannot be
# enabled by default. See the following link for details:
# http://who-t.blogspot.com/2010/11/how-to-ignore-configuration-errors.html
#       MatchDevicePath "/dev/input/event*"
        Option "VertScrollDelta" "16"
        Option "HorizScrollDelta" "16"
EndSection
```

```
Section "InputClass"
        Identifier "touchpad catchall"
        Driver "synaptics"
        MatchIsTouchpad "on"
# This option is recommend on all Linux systems using evdev, but cannot be
# enabled by default. See the following link for details:
# http://who-t.blogspot.com/2010/11/how-to-ignore-configuration-errors.html
      MatchDevicePath "/dev/input/event*"
	# Ajout souris logitech
	Option "VertScrollDelta" "52"
	Option "HorizScrollDelta" "52"	
EndSection
```
