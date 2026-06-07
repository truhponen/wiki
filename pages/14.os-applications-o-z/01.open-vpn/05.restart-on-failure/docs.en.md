---
title: 'Restart on failure'
date: '20:44 22-12-2024'
taxonomy:
    category:
        - docs
---

Instructions based on: https://www.digitalocean.com/community/tutorials/how-to-configure-a-linux-service-to-start-automatically-after-a-crash-or-reboot-part-2-reference

    sudo nano /etc/systemd/system/multi-user.target.wants/openvpnas.service

set in "Service"-section

    Restart=on-failure

To test setup find main PID

    sudo systemctl status openvpnas.service

Kill main process

    sudo kill -9 [add PID number here]

Check if process comes back alive

    sudo systemctl status openvpnas.service
