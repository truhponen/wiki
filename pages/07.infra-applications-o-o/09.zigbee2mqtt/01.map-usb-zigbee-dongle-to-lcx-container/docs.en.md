---
title: 'Map USB Zigbee Dongle to LCX-container'
date: '07:08 06-01-2025'
taxonomy:
    category:
        - docs
---

1. Check where USB device is connected

        ls -l /dev/serial/by-id

2. Result is something like ...

    `lrwxrwxrwx 1 root root 13 Nov  7 17:07 usb-ITead_Sonoff_Zigbee_3.0_USB_Dongle_Plus_d26ec6380919ec119f4839cc47486eb0-if00-port0 -> ../../ttyUSB0`

3. Check details of "file" that represents connection...

        ls -l /dev/ttyUSB0

4. Result is something like. Pay attention to number (in my case 188) ...

    `crw-rw---- 1 root root 188, 0 Nov  7 18:18 /dev/ttyUSB0`

5. Edit container configuration

        nano /etc/pve/lxc/101.conf

6. Add two rows. In first line you need number: In second line you need "file".

    `lxc.cgroup.devices.allow: c 188:* rwm`

    `lxc.mount.entry: /dev/ttyUSB0 dev/ttyUSB0 none bind,optional,create=file`

7. Update Zigbee2MQTT's "configuration.yaml"

       port: /dev/ttyUSB0

# Making USB usable in LXC-container (NEW)

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