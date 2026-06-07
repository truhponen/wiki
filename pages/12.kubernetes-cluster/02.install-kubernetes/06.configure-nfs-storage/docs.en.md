---
title: 'Configure NFS storage'
date: '21:12 30-01-2025'
taxonomy:
    category:
        - docs
---

[CSI-driver NFS](/csi-driver-nfs) needs to be installed

1. [Setup NFS share](/nfs/zfs-nfs)

2. Create PersistentVolumeClaim

   * Example: [https://raw.githubusercontent.com/truhponen/home/refs/heads/main/base/PersistentVolumeClaim.yaml](https://raw.githubusercontent.com/truhponen/home/refs/heads/main/base/PersistentVolumeClaim.yaml)
   * It seems that Size of PersistentVolumeClaim and PersistentVolume needs to be the same

3. Create PersistentVolume

   * Example: [https://raw.githubusercontent.com/truhponen/home/refs/heads/main/base/PersistentVolume-prod.yaml](https://raw.githubusercontent.com/truhponen/home/refs/heads/main/base/PersistentVolume-prod.yaml)
   * AccessMode "ReadWriteMany" is important if there is multiple containers using same claim