---
title: 'Setting up Proxmox node'
date: '21:07 22-12-2024'
taxonomy:
    category:
        - docs
---

1. Create node with ZFS-file system

2. Create udev rule that make USB devices exposable to containers (modify uid and gid)

   Create udev rule-file

       nano /etc/udev/rules.d/usb-ITead_Sonoff_Zigbee.rules

   Add row

       SUBSYSTEM=="tty", ATTRS{removable}=="removable", OWNER="100000", GROUP="100000"

   * "tty" refers to USB
   * "removable" distinguish removable devices

   Reload udev rules

       udevadm control --reload

   Unplug and plug USB device or retrigger rule

       udevadm trigger

   Check owner of file...

       ls -al /dev/ttyUSB0

   Result is something like ...

   `crw-rw---- 1 100000 100000 188, 0 Nov  7 18:18 /dev/ttyUSB0`