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


3. Mount Lacie Cloud box in fstab. This has to be done on OS level as SMB version 1 is not supported by Proxmox

        //192.168.xxx.xxx/Family /mnt/lacie-cloudbox cifs vers=1.0,username=[username],password=[password],file_mode=0755,dir_mode=0755,uid=100000,gid=100000  0  0

4. Mount Config shares in fstab because Proxmox doesn't allow control of uid and gid values

        //192.168.xxx.xx1/config /mnt/config/101 cifs username=[username],password=[password],file_mode=0755,dir_mode=0755,uid=100000,gid=100000  0  0
        //192.168.xxx.xx2/config /mnt/config/103 cifs username=[username],password=[password],file_mode=0755,dir_mode=0755,uid=100000,gid=100000  0  0
        //192.168.xxx.xx3/config /mnt/config/104 cifs username=[username],password=[password],file_mode=0755,dir_mode=0755,uid=100000,gid=100000  0  0
        //192.168.xxx.xx4/config /mnt/config/105 cifs username=[username],password=[password],file_mode=0755,dir_mode=0755,uid=100000,gid=100000  0  0
        //192.168.xxx.xx5/config /mnt/config/106 cifs username=[username],password=[password],file_mode=0755,dir_mode=0755,uid=100000,gid=100000  0  0
        //192.168.xxx.xx6/config /mnt/config/107 cifs username=[username],password=[password],file_mode=0755,dir_mode=0755,uid=100000,gid=100000  0  0