---
title: 'Making USB usable in LXC-container 2'
date: '07:08 06-01-2025'
taxonomy:
    category:
        - docs
---

### New way

Goal is to change owner and group of files representing USB-device

In node's CLI

1. Create udev rule-file

        nano /etc/udev/rules.d/usb-ITead_Sonoff_Zigbee.rules

2. Add row

        SUBSYSTEM=="tty", ATTRS{removable}=="removable", OWNER="100000", GROUP="100000"

* "tty" refers to USB
* "removable" distinguish removable devices

3. Reload udev rules

        udevadm control --reload

4. Unplug and plug USB device or retrigger rule

        udevadm trigger

7. Check owner of file...

        ls -al /dev/ttyUSB0

8. Result is something like ...

    `crw-rw---- 1 100000 100000 188, 0 Nov  7 18:18 /dev/ttyUSB0`

7. Restart container - I used browser UI

### Useful udev commands

* Debugging

        udevadm test $(udevadm info -q path -n /dev/ttyUSB0)

* Check attributes

        udevadm info /dev/ttyUSB0

* Check details of path

        udevadm info -a /dev/bus/usb/001/022

* 001 and 002 you find with 

        lsusb

# Making USB usable in LXC-container (OLD)

Problem of this approach is that you need to CHOWN file every time USB device is removed 

In node's CLI

1. Change owner to user 100000 and group 100000. This means that in container root owns file. If not changed owner in container is "nobody" and program running in container cannot use device.

        chown 100000:100000 /dev/ttyUSB0

2. Result is something like ...

    `crw-rw---- 1 100000 100000 188, 0 Nov  7 18:18 /dev/ttyUSB0`

  

# Making Sonoff ZBDongle-E a router

I used https://www.vandyke.com/products/securecrt/ for flashing...

In general these were good instructions...
 
https://sonoff.tech/wp-content/uploads/2022/11/SONOFF-Zigbee-3.0-USB-dongle-plus-firmware-flashing-.pdf

Only thing I would clarify 

"Keep pressing the Boot button, restart the device..." to "Keep pressing the Boot button and press restart button at the same time."