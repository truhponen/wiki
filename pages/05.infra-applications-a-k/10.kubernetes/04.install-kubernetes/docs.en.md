---
title: 'Install Kubernetes'
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
    
Make sure that configs exist for kubernetes user

echo "|"
echo "Install Flannel with defauld CIDR"
echo "|"
kubectl apply -f https://github.com/flannel-io/flannel/releases/latest/download/kube-flannel.yml

kubeadm join 192.168.68.160:6443 --token c6fpgz.dfnujkwgq9hwt604 \
        --discovery-token-ca-cert-hash sha256:a1e8df44f4bbc92a9f492d7d8709b10c83f0c744ea755a17b95e5cbf42d10d02 