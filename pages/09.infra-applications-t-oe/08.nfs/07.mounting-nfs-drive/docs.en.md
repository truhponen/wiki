---
title: 'Mounting NFS drive'
date: '18:48 21-12-2024'
taxonomy:
    category:
        - docs
---

## Mounting NFS drive

Followed these instructions:
* https://cloudinfrastructureservices.co.uk/how-to-install-nfs-on-debian-11-server/
* https://www.atlantic.net/dedicated-server-hosting/how-to-install-and-configure-nfs-server-on-debian-11/

### Steps

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