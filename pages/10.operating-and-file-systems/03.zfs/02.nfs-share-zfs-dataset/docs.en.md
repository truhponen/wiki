---
title: 'NFS share ZFS dataset'
date: '18:48 21-12-2024'
taxonomy:
    category:
        - docs
---

#### Set sharenfs value

    zfs set sharenfs="rw=@192.168.68.0/24,rw,sync,no_subtree_check,no_root_squash" rpool/kubernetes
 
```rw``` stands for read and write access

```sync``` changes are notified only after changes have been stored to stable storage

```no_subtree_check``` is default value but just stated explicitly

```no_root_squash``` allows root user on the client side have root rights on host side. If not set, root user of other system will fail to manipulate file system.
   
#### Make sharenfs value inherited

    zfs inherit sharenfs rpool/kubernetes/analytics