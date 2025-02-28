---
title: 'If user configs are lost'
date: '11:45 27-01-2025'
taxonomy:
    category:
        - docs
---

Make sure that configs exist for kubernetes user

based on https://stackoverflow.com/questions/54841703/kubernetes-lost-kube-config

    kubeadm alpha phase kubeconfig admin --kubeconfig-dir /etc/kubernetes --cert-dir /etc/kubernetes/pki
    
Copy configs are in home directory of user $HOME/.kube/config

Configs can be copied from Kubernetes-folder 

    mkdir -p $HOME/.kube
    sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
    sudo chown $(id -u):$(id -g) $HOME/.kube/config