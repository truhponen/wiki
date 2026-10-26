---
title: 'CSI-driver NFS'
date: '21:31 27-02-2025'
routes:
    default: /csi-driver-nfs
---

"CSI NFS" is Container Storage Interface that allocates [NFS shares](/nfs) Persistent Storages to PersistentVolumeClaims

	helm repo update csi-driver-nfs

	helm search repo csi-driver-nfs --versions
	
    helm install csi-driver-nfs csi-driver-nfs/csi-driver-nfs --namespace csi-driver-nfs --version [add here the version]

source: [https://github.com/kubernetes-csi/csi-driver-nfs](https://github.com/kubernetes-csi/csi-driver-nfs)