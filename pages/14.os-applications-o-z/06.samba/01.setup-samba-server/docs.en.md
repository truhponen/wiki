---
title: 'Setup Samba server'
date: '20:54 22-12-2024'
taxonomy:
    category:
        - docs
---

from [https://wiki.alpinelinux.org/wiki/Setting_up_a_Samba_server](https://wiki.alpinelinux.org/wiki/Setting_up_a_Samba_server)

Archive old configuration

    mv /etc/samba/smb.conf /etc/samba/smb.conf.old

create new configuration

    nano /etc/samba/smb.conf

Content of configuration

    [config-shared]
    # to follow symlinks
    follow symlinks = yes
    # to allow symlinks from outside
    wide links = yes
    browseable = yes
    writeable = yes
    force user = root
    force create mode = 0755
    force directory mode = 0755
    path = /config-local

Create user

    adduser samba

Add Samba password

    smbpasswd -a samba