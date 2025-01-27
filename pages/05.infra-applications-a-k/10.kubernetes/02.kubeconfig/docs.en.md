---
title: Kubeconfig
date: '07:34 27-01-2025'
taxonomy:
    category:
        - docs
---

https://stackoverflow.com/questions/54841703/kubernetes-lost-kube-config

    kubeadm alpha phase kubeconfig admin --kubeconfig-dir /etc/kubernetes --cert-dir /etc/kubernetes/pki
    
    mkdir -p $HOME/.kube
    sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
    sudo chown $(id -u):$(id -g) $HOME/.kube/config