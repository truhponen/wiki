---
title: Flannel
date: '11:45 27-01-2025'
taxonomy:
    category:
        - docs
routes:
    default: /flannel
---

Flannel provides container networking. In practice, it assigns IPs for containers.

Install Flannel CNI

    kubectl apply -f https://github.com/flannel-io/flannel/releases/latest/download/kube-flannel.yml