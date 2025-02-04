---
title: Backups
date: '21:49 21-12-2024'
taxonomy:
    category:
        - docs
routes:
    default: /backups
---

There is several approaches to backups.

* Photos are backed up to [ZFS](/zfs) raid
* [LXC containers](/lxc) running in [Proxmox](/proxmox) are backed up with [Proxmox Backup Server](/proxmox-backup-server). Some copies of backups are replicated to [ZFS](/zfs) raid.