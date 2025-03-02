---
title: 'Configuring storage'
date: '09:52 01-02-2025'
taxonomy:
    category:
        - docs
---

Remove claim from persistent volume

    kubectl patch pv pv-for-rabbitmq -p '{"spec":{"claimRef": null}}'

Used for static provisioning

Persistent volume: [https://raw.githubusercontent.com/kubernetes-csi/csi-driver-nfs/master/deploy/example/pv-nfs-csi.yaml](https://raw.githubusercontent.com/kubernetes-csi/csi-driver-nfs/master/deploy/example/pv-nfs-csi.yaml)

Persistent volume claim: [https://raw.githubusercontent.com/kubernetes-csi/csi-driver-nfs/master/deploy/example/pvc-nfs-csi-static.yaml](https://raw.githubusercontent.com/kubernetes-csi/csi-driver-nfs/master/deploy/example/pvc-nfs-csi-static.yaml)