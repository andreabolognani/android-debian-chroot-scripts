android-debian-chroot-scripts
=============================

The name says it all, really. A couple of scripts to make running a Debian
chroot on Android less of a chore.


Prerequisites
-------------

  * root must be available
  * busybox must have certain commands compiled in

Both will be checked at runtime. Tested on CyanogenMod 11.


Installation
------------

Drop the contents of the repository somewhere on your device.
I like `/sdcard/debian`, but the scripts are smart enough to detect the
installation directory so it doesn't really matter.

Create a directory named `images` inside the installation directory, and
drop your Debian images in there. Images must have `.img` extension.


Usage
-----

The scripts must be run as root.

The only parameter accepted is the name of the Debian image, eg. use

    # sh start testing

to mount `testing.img`. If the parameter is omitted, `default.img` will be
used instead. Multiple chroots can be run concurrently, but only one chroot
per image is allowed at any given time.

The OpenSSH daemon will be started and stopped if available inside the
chroot. If you plan to run multiple chroots at the same time, make sure each
is configured so that the OpenSSH daemon listens on a different port.


Bugs
----

Quite possibly.


License
-------

This program is free software; you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation; either version 2 of the License, or
(at your option) any later version.
