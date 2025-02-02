---
title: 'Incus profile for Kubernetes'
date: '08:48 02-02-2025'
taxonomy:
    category:
        - docs
---

name: k8s
description: Incus profile for Kubernetes
devices:
  eth0:
    name: eth0
    nictype: bridged
    parent: incusbr0
    type: nic
  kmsg:
    path: /dev/kmsg
    source: /dev/kmsg
    type: unix-char
  root:
    path: /
    pool: data-incus
    type: disk
config:
  limits.cpu: '2'
  limits.memory: 4GB
  limits.memory.swap: 'false'
  security.privileged: 'true'
  security.nesting: 'true'
  linux.kernel_modules: ip_tables,ip6_tables,nf_nat,overlay,br_netfilter
  raw.lxc: >-
    incus.apparmor.profile=unconfined nlxc.cap.drop= 
    nlxc.cgroup.devices.allow=a nlxc.mount.auto=proc:rw sys:rw
project: default