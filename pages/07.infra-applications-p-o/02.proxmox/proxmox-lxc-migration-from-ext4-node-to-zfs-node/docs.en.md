---
title: 'Proxmox LXC migration from ext4‐node to zfs‐node'
date: '21:05 22-12-2024'
taxonomy:
    category:
        - docs
---

### Problem 

When trying to migrate LXC from command line using ...

    pct migrate [ID] [name of zfs-node] --target-storage [name of storage]

... you get error `ERROR: migration aborted (duration 00:00:00): storage migration for 'local-lvm...' to storage '[name of storage]' failed - cannot migrate from storage type 'lvmthin' to 'zfspool'`

### One solution

Migrate LXCs using Proxmox Backup Server (PBS)

#### Steps

Configure both nodes to use same backup Datastore.

1. Create user


Set zfs-node as "DatastoreAdmin" in PBS so that it sees backups of ext4-node.