---
title: '1. Bootstrap cluster'
date: '11:45 27-01-2025'
taxonomy:
    category:
        - docs
---

#### Bootstrap cluster

related shell script https://github.com/truhponen/home/blob/main/kubernetes/kubernetes-crio-flannel.sh

Run as kubernetes sudo user

Install basics:
* Container runtime: cri-o
* Kubernetes node agent: kubelet
* Kubernetes build tool: kubeadm
* Kubernetes command line tool: kubectl
* Kubernetes application management tool: helm

Make important host configs

    swapoff -a
    modprobe br_netfilter
    sysctl -w net.ipv4.ip_forward=1

Run init with default CIDR

    kubeadm init --pod-network-cidr=10.244.0.0/16