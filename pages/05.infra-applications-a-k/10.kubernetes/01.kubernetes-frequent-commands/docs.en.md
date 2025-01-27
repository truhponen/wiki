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

Get details of single or all nodes (helps when status of node is NotReady)

    kubectl describe node dell-optiplex-5050

    kubectl describe nodes
 
 Get pods from a namespace or all namespaces
 
    kubectl get pods --namespace=kube-system
 
    kubectl get pods -A
  
 
    kubectl apply -f https://raw.githubusercontent.com/truhponen/home/refs/heads/main/kubernetes/purelb/servicegroup-default.yaml
 
    kubectl apply -f https://raw.githubusercontent.com/truhponen/home/refs/heads/main/kubernetes/purelb/test-configuration.yaml