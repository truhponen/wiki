---
title: 'Useful udev commands 2'
date: '07:08 06-01-2025'
taxonomy:
    category:
        - docs
---

* Debugging

        udevadm test $(udevadm info -q path -n /dev/ttyUSB0)

* Check attributes

        udevadm info /dev/ttyUSB0

* Check details of path

        udevadm info -a /dev/bus/usb/001/022

* 001 and 002 you find with 

        lsusb


  

# Making Sonoff ZBDongle-E a router

I used https://www.vandyke.com/products/securecrt/ for flashing...

In general these were good instructions...
 
https://sonoff.tech/wp-content/uploads/2022/11/SONOFF-Zigbee-3.0-USB-dongle-plus-firmware-flashing-.pdf

Only thing I would clarify 

"Keep pressing the Boot button, restart the device..." to "Keep pressing the Boot button and press restart button at the same time."