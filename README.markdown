[![This project is considered stable](https://img.shields.io/badge/Status-stable-green.svg)](https://arp242.net/status/stable)
[![Build Status](https://travis-ci.org/Carpetsmoker/find-cursor.svg?branch=master)](https://travis-ci.org/Carpetsmoker/find-cursor)

Simple XLib program to highlight the cursor position. This is similar to the
feature found in Windows XP (and possibly later?)

![screenshot.gif](https://raw.githubusercontent.com/Carpetsmoker/find-cursor/master/screenshot.gif)

Installation
============

Compile it by typing `make`, install it with `make install`. There are some
packages:

- [FreeBSD](https://www.freshports.org/x11/find-cursor/)
- [Void Linux](https://github.com/biopsin/void-packages/tree/master/srcpkgs/find-cursor)

Usage
=====

See `find-cursor(1)` or `find-cursor -h` to see some options for controlling the
appearance.

Launching
=========

You will want to map a key in your window manager to run `find-cursor`. You can
also use [`xbindkeys`](xbindkeys), which should work with `$any` window manager.

I run it with [`xcape`][xcape]:

	xcape -e 'Control_L=Escape;Shift_L=KP_Add'

When `Left Shift` is tapped a `Keypad Add` is sent; I configured my window
manager to launch `find-cursor` with that.

I don't have a numpad on my keyboard; you can also use `F13` or some other
unused key.

Compton
=======

You may want to disable shadows if you use compton or some other composite
manager; for example for compton start it with:

	compton --shadow-exclude "class_g = 'find-cursor'"

Or, perhaps even better, disable it for all shaped windows:

	compton --shadow-exclude 'bounding_shaped'

You can also put that in the compton config file. Other managers might have
different options/flags.

[xcape]: https://github.com/alols/xcape
[xbindkeys]: http://www.nongnu.org/xbindkeys/xbindkeys.html
