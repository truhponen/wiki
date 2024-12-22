---
title: 'Setup Samba client'
date: '20:55 22-12-2024'
taxonomy:
    category:
        - docs
---

Based on 
* https://raspberrypi.stackexchange.com/questions/40974/access-network-samba-share-from-pi-client
* https://dev.to/oswllt/proxmox-bind-smb-mount-to-unprivileged-lxc-container-the-easy-way-3l4k

Edit fstab

    nano /etc/fstab


file_mode=0755,dir_mode=0755,uid=1000,gid=1000 

    //192.168.xxx.xxx/share  /path/to/folder cifs credentials=/path/to/.smbcredentials,file_mode=0755,dir_mode=0755,uid=1000,gid=1000  0  0

Test mount

    findmnt --verify

Or

    mount -a

Reload services

    

Mount 

    mount -t cifs -o vers=1.0,username=[username] //192.168.xxx.xxx/Family /mnt/lacie-cloudbox