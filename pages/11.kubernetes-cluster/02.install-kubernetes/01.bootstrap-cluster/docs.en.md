---
title: 'Bootstrap cluster'
date: '11:45 27-01-2025'
taxonomy:
    category:
        - docs
---

#### Bootstrap cluster

Shell script

    curl https://raw.githubusercontent.com/truhponen/home/refs/heads/main/cluster/bootstrap-bare-metal-cluster.sh | bash

Run as kubernetes sudo user

Installs basics:
* Container runtime: cri-o
* Kubernetes node agent: kubelet
* Kubernetes build tool: kubeadm
* Kubernetes command line tool: kubectl
* Kubernetes "application management" tool: [helm](/helm)
* [Flannel](/flannel) container networking with Helm
* [PureLB](/purelb) bare metal loadbalancer with Helm
* [Traefik](/traefik) Ingress controller and customizations with Helm

Make important host configs

    swapoff -a
    modprobe br_netfilter
    sysctl -w net.ipv4.ip_forward=1

Run init with default CIDR

    kubeadm init --pod-network-cidr=10.244.0.0/16