---
title: 'Kubernetes frequent commands'
date: '16:59 25-01-2025'
taxonomy:
    category:
        - docs
---

Config that are needed after reboot. Run as root.

    swapoff -a
    modprobe br_netfilter
    
Permanent change for "swapoff -a": comment out swap from /etc/fstab
 
Permanent change for "modprobe br_netfilter": comment out swap from /etc/fstab

Check previous. Run as root.

    lsmod | grep netfilt
    swapon --show

Add shorthands

    alias k="kubectl" d="kubectl describe" g="kubectl get" a="kubectl apply"

Access to container

    kubectl exec --stdin --tty grav-0 -- /bin/bash

Stop application by scaling statefulset to 0 replicas

    kubectl scale statefulset.apps/influxdb -n analytics --replicas=0

Get cluster information

    kubectl cluster-info
    
List nodes

    kubectl get nodes

Get details of single node (helps when status of node is NotReady)

    kubectl describe node dell-optiplex-5050

Get details of all nodes (helps when status of node is NotReady)

    kubectl describe nodes
 
Get pods from a namespace or all namespaces
 
    kubectl get pods --namespace=kube-system

Get pods from all namespaces
 
    kubectl get pods -A