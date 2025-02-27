---
title: 'Configure NFS storage'
date: '21:12 30-01-2025'
taxonomy:
    category:
        - docs
---

[Setup NFS share](/nfs/zfs-nfs)

Chown folder

Add CSI driver repo

    helm repo add csi-driver-nfs https://raw.githubusercontent.com/kubernetes-csi/csi-driver-nfs/master/charts

Install CSI driver

    helm install csi-driver-nfs csi-driver-nfs/csi-driver-nfs --namespace kube-system --version v4.10.0

Validate that controller are running 

    kubectl -n kube-system get pod -o wide -l app=csi-nfs-controller

Validate that controller are running

    kubectl -n kube-system get pod -o wide -l app=csi-nfs-node

Apply storage class

    kubectl apply -f https://github.com/truhponen/home/blob/main/kubernetes/storage-class-kubernetes-nfs.yaml

Test setup e.g. applying Kubernetes ["Creating a StatefulSet"-tutorial ](https://kubernetes.io/docs/tutorials/stateful-application/basic-stateful-set/#creating-a-statefulset)

    kubectl apply -f https://k8s.io/examples/application/web/web.yaml