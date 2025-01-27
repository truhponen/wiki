---
title: 'Install Kubernetes'
date: '11:45 27-01-2025'
taxonomy:
    category:
        - docs
---

### Install basics

Basics:
* Container runtime: cri-o
* Kubernetes node agent: kubelet
* Kubernetes build tool: kubeadm
* Kubernetes command line tool: kubectl
* Kubernetes application management tool: helm

* related shell script https://github.com/truhponen/home/blob/main/kubernetes/kubernetes-crio-flannel.sh

1. apt-repositories


kubeadm join 192.168.68.160:6443 --token c6fpgz.dfnujkwgq9hwt604 \
        --discovery-token-ca-cert-hash sha256:a1e8df44f4bbc92a9f492d7d8709b10c83f0c744ea755a17b95e5cbf42d10d02 