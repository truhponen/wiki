---
title: rsync
date: '21:00 22-12-2024'
taxonomy:
    category:
        - docs
routes:
    default: /rsync
---

Sync current folder (.) to another machine (192.168.68.150)

    rsync -av . root@192.168.68.150:/rpool/kubernetes/prod/

Using asterisk results in excluding hidden files  

    rsync -av /kube-storage/analytics/* root@192.168.68.150:/rpool/kubernetes/analytics/

Omitting trailing slash copies "analytics"-folder also, not just content 

    rsync -av /kube-storage/analytics root@192.168.68.150:/rpool/kubernetes/
