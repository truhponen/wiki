---
title: 'Kubernetes frequent commands'
date: '16:59 25-01-2025'
taxonomy:
    category:
        - docs
---



Install Flannel (https://github.com/flannel-io/flannel)

    kubectl apply -f https://github.com/flannel-io/flannel/releases/latest/download/kube-flannel.yml

Get cluster information

    kubectl cluster-info
    
List nodes

    kubectl get nodes

Get details of single or all nodes (helps when status of node is NotReady=)

    kubectl describe node dell-optiplex-5050

    kubectl describe nodes