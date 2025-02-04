---
title: 'Not working - Install Kubernetes in Incus LXC container'
date: '07:25 02-02-2025'
taxonomy:
    category:
        - docs
---


1. Change nf_conntrack_max

   Not sure if needed, but was recommended in https://github.com/justmeandopensource/kubernetes/blob/master/lxd-provisioning/README.md. I had troubles with kube-proxy giving error related "Set sysctl" entry="net/netfilter/nf_conntrack_max" value=131072: not permitted. This was before I changed "lxc.apparmor.profile" to "incus.apparmor.profile"

       sudo sysctl -w net.netfilter.nf_conntrack_max=524288

2. Create containers using profile [k8s](https://github.com/truhponen/home/blob/main/incus/k8s)

3. After container started add profile [k8s-preflight](https://github.com/truhponen/home/blob/main/incus/k8s-preflight)
   
   Profile is basically same as [k8s](https://github.com/truhponen/home/blob/main/incus/k8s) with additional device mappings, at least, preflight will fail. Device mappings were copied from https://microk8s.io/docs/install-lxd.

4. Install http-utils

       apt update
       apt install -y software-properties-common curl

5. Execute shell script

       bash <(curl https://raw.githubusercontent.com/truhponen/home/main/kubernetes/install-in-Incus-LXC/crio-kubernetes.sh)

   Init has flag `--pod-network-cidr=10.244.0.0/16` for Flannel

6. Setup configs

       mkdir -p $HOME/.kube
       sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
       sudo chown $(id -u):$(id -g) $HOME/.kube/config

7. Install Helm

       curl https://baltocdn.com/helm/signing.asc | gpg --dearmor | sudo tee /usr/share/keyrings/helm.gpg > /dev/null
       sudo apt-get install apt-transport-https --yes
       echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/helm.gpg] https://baltocdn.com/helm/stable/debian/ all main" | sudo tee /etc/apt/sources.list.d/helm-stable-debian.list
       apt update
       apt install helm

8. Install Flannel using Helm

       kubectl create ns kube-flannel
       kubectl label --overwrite ns kube-flannel pod-security.kubernetes.io/enforce=privileged

       helm repo add flannel https://flannel-io.github.io/flannel/
       helm install flannel --set podCidr="10.244.0.0/16" --namespace kube-flannel flannel/flannel

9. Pod network

       https://kubernetes.io/docs/concepts/cluster-administration/addons/

10. Join workers

        kubeadm join 10.12.96.118:6443 --token 3dy8nl.g3c... \
         --discovery-token-ca-cert-hash sha256:d54...
