---
title: 'Configuring storage'
date: '09:52 01-02-2025'
taxonomy:
    category:
        - docs
---

Uses NFS storage class

[https://kubernetes.io/docs/concepts/storage/storage-classes/#nfs](https://kubernetes.io/docs/concepts/storage/storage-classes/#nfs)

Uses recommended NFS CSI driver for Kubernetes
[https://github.com/kubernetes-csi/csi-driver-nfs#readme](https://github.com/kubernetes-csi/csi-driver-nfs#readme)

Installed with helm chart
[https://github.com/kubernetes-csi/csi-driver-nfs/tree/master/charts](https://github.com/kubernetes-csi/csi-driver-nfs/tree/master/charts)

Used for static provisioning

Persistent volume: [https://raw.githubusercontent.com/kubernetes-csi/csi-driver-nfs/master/deploy/example/pv-nfs-csi.yaml](https://raw.githubusercontent.com/kubernetes-csi/csi-driver-nfs/master/deploy/example/pv-nfs-csi.yaml)

Persisten volume claim: [https://raw.githubusercontent.com/kubernetes-csi/csi-driver-nfs/master/deploy/example/pvc-nfs-csi-static.yaml](https://raw.githubusercontent.com/kubernetes-csi/csi-driver-nfs/master/deploy/example/pvc-nfs-csi-static.yaml)