---
title: 'NFS share ZFS dataset'
date: '18:48 21-12-2024'
taxonomy:
    category:
        - docs
---

Set sharenfs value

    zfs set sharenfs="rw=@192.168.68.0/24,rw,sync,no_subtree_check,no_root_squash" oricopool-1/backup
   
Make sharenfs value inherited

    zfs inherit sharenfs rpool/kubernetes/analytics