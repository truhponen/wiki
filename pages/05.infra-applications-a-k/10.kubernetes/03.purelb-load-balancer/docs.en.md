---
title: 'PureLB load balancer'
date: '07:40 27-01-2025'
taxonomy:
    category:
        - docs
---

Installation

source: https://purelb.gitlab.io/purelb/install/install/

1. Install with Helm

2. Create Servicegroup to define configurations how public IPs are assigned

    kubectl apply -f https://raw.githubusercontent.com/truhponen/home/refs/heads/main/kubernetes/purelb/servicegroup-default.yaml

Some test

    kubectl apply -f https://raw.githubusercontent.com/truhponen/home/refs/heads/main/kubernetes/purelb/test-configuration.yaml