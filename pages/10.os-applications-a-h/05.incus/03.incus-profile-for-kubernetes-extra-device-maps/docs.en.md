---
title: 'Incus profile for Kubernetes - extra device maps'
date: '08:44 02-02-2025'
taxonomy:
    category:
        - docs
---

```
name: k8s-preflight
description: Incus profile for Kubernetes with some extra device maps
devices:
  apparmor-disable1:
    path: /sys/module/nf_conntrack/parameters/hashsize
    source: /sys/module/nf_conntrack/parameters/hashsize
    type: disk
  apparmor-disable2:
    path: /sys/fs/bpf
    source: /sys/fs/bpf
    type: disk
  apparmor-disable3:
    path: /proc/sys/net/netfilter/nf_conntrack_max
    source: /proc/sys/net/netfilter/nf_conntrack_max
    type: disk
  apparmor-disable4:
    path: /boot/config-6.8.0-41-generic
    source: /boot/config-6.8.0-41-generic
    type: disk
  apparmor-disable5:
    path: /lib/modules/6.8.0-41-generic
    source: /lib/modules/6.8.0-41-generic
    type: disk
  ```