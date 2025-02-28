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

#### 3. Install Container networking, bare metal load balancer, ingress controller and CSI-driver for NFS using Helm

If you have only single node

    kubectl taint nodes $(hostname) node-role.kubernetes.io/control-plane:NoSchedule-

    curl https://raw.githubusercontent.com/truhponen/home/refs/heads/main/cluster/3-add-cluster-applications.sh | bash