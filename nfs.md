---
title: NFS
description: 
published: true
date: 2024-12-18T10:47:57.713Z
tags: 
editor: markdown
dateCreated: 2024-12-18T10:47:57.713Z
---

# ZFS NFS

Install kernel server

    apt install nfs-kernel-server

Set sharenfs value

    zfs set sharenfs="rw=@192.168.68.0/24" oricopool-1/backup


# Mounting NFS drive

Followed these instructions:
* https://cloudinfrastructureservices.co.uk/how-to-install-nfs-on-debian-11-server/
* https://www.atlantic.net/dedicated-server-hosting/how-to-install-and-configure-nfs-server-on-debian-11/

## Steps

1. Create folder

2. Add to "exports"-file...

       sudo nano /etc/exports

3. ... a statement that allows NFS-connections to folder

        /nfs/postgres 192.168.68.0/24(rw,sync,no_subtree_check,no_root_squash)

4. Restart NFS server

        sudo systemctl restart nfs-server
        
5. Create volume in Docker / Portainer

   Use NFS volume

       TRUE

   Address

       192.168.68.118

   Mount point

       :/nfs/whisper

# NFS Client

You need nfs-common

    apt-get install nfs-common -y

Create mount

    mount 192.168.68.118:/nfs /nfs

# Useful commands

Check applicable NSF config

    cat /var/lib/nfs/etab