---
title: 'Install Kubernetes - User configs'
date: '11:45 27-01-2025'
taxonomy:
    category:
        - docs
---

#### Create kubernetes user to control plane host

#### Bootstrap cluster

related shell script https://github.com/truhponen/home/blob/main/kubernetes/kubernetes-crio-flannel.sh

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
    
#### Make sure that configs exist for kubernetes user

based on https://stackoverflow.com/questions/54841703/kubernetes-lost-kube-config

Create configs

    kubeadm alpha phase kubeconfig admin --kubeconfig-dir /etc/kubernetes --cert-dir /etc/kubernetes/pki

Copy configs to home directory of user

    mkdir -p $HOME/.kube
    sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
    sudo chown $(id -u):$(id -g) $HOME/.kube/config

#### Install must-have aplications

Flannel CNI

    kubectl apply -f https://github.com/flannel-io/flannel/releases/latest/download/kube-flannel.yml

PureLB load balancer

1. Install with helm https://purelb.gitlab.io/purelb/install/install/
2. Define configurations https://purelb.gitlab.io/purelb/install/config/

       kubectl apply -f https://raw.githubusercontent.com/truhponen/home/refs/heads/main/kubernetes/purelb/servicegroup-default.yaml

#### Add nodes to cluster

kubeadm join 192.168.68.160:6443 --token c6fpgz.dfnujkwgq9hwt604 \
        --discovery-token-ca-cert-hash sha256:a1e8df44f4bbc92a9f492d7d8709b10c83f0c744ea755a17b95e5cbf42d10d02 