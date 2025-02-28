---
title: 'User configs'
date: '11:45 27-01-2025'
taxonomy:
    category:
        - docs
---

Make sure that configs exist for kubernetes user

based on https://stackoverflow.com/questions/54841703/kubernetes-lost-kube-config

Copy configs to home directory of user

    mkdir -p $HOME/.kube
    sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
    sudo chown $(id -u):$(id -g) $HOME/.kube/config
 
If there is need you can create configs

    kubeadm alpha phase kubeconfig admin --kubeconfig-dir /etc/kubernetes --cert-dir /etc/kubernetes/pki