---
title: 'ZFS NFS'
date: '18:48 21-12-2024'
taxonomy:
    category:
        - docs
---

## ZFS NFS

Install kernel server

    apt install nfs-kernel-server

Set sharenfs value

    zfs set sharenfs="rw=@192.168.68.0/24" oricopool-1/backup