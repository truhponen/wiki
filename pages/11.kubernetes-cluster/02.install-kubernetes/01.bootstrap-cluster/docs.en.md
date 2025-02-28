---
title: 'Bootstrap cluster'
date: '11:45 27-01-2025'
taxonomy:
    category:
        - docs
---

#### 1. Install Container runtime Cri-o, Kubelet, Kubeadm, Kubectl and Helm and initializes Kubernetes

Run as root

    sudo -i

    curl https://raw.githubusercontent.com/truhponen/home/refs/heads/main/cluster/1-bootstrap-bare-metal-cluster.sh | bash

#### 2. Configure admin user

Run as admin user

    curl https://raw.githubusercontent.com/truhponen/home/refs/heads/main/cluster/2-create-user-configurations | bash

#### Add nodes to cluster

kubeadm join 192.168.68.160:6443 --token c6fpgz.dfnujkwgq9hwt604 \
        --discovery-token-ca-cert-hash sha256:a1e8df44f4bbc92a9f492d7d8709b10c83f0c744ea755a17b95e5cbf42d10d02 
        
If you have only single node

    kubectl taint nodes $(hostname) node-role.kubernetes.io/control-plane:NoSchedule-

#### 3. Install Container networking, bare metal load balancer, ingress controller and CSI-driver for NFS using Helm

    curl https://raw.githubusercontent.com/truhponen/home/refs/heads/main/cluster/3-add-cluster-applications.sh | bash