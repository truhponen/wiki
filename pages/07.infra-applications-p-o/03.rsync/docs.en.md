---
title: rsync
date: '21:00 22-12-2024'
taxonomy:
    category:
        - docs
routes:
    default: rsync
---

 
    rsync -av /mnt/lacie-cloudbox/Elvis/* /oricopool-1/media/documents/elvis > ~/transfer-elvis.log 2>&1 &

Using asterisk results in excluding hidden files

    rsync -av /mnt/lacie-cloudbox/Elvis/ /oricopool-1/media/documents/elvis > ~/transfer-elvis.log 2>&1 &