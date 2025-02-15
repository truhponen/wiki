---
title: 'Install Kubernetes'
date: '11:45 27-01-2025'
taxonomy:
    category:
        - docs
---



1. Create kubernetes user to control plane host

2. Bootstrap cluster
    
        curl https://raw.githubusercontent.com/truhponen/home/refs/heads/main/bash/kubernetes-crio-flannel.sh | bash

3. Make sure that configs exist for kubernetes user



4. Install must-have aplications

5. Add nodes to cluster


Install Flannel (https://github.com/flannel-io/flannel)

    kubectl apply -f https://github.com/flannel-io/flannel/releases/latest/download/kube-flannel.yml