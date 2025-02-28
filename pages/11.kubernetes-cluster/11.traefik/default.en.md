---
title: Traefik
date: '20:45 27-02-2025'
---

Sources:
- [https://doc.traefik.io/traefik/getting-started/install-traefik/](https://doc.traefik.io/traefik/getting-started/install-traefik/)
- [https://github.com/traefik/traefik-helm-chart/blob/master/EXAMPLES.md](https://github.com/traefik/traefik-helm-chart/blob/master/EXAMPLES.md)

With default chart

    helm install traefik traefik/traefik --create-namespace -n traefik

With customizations

    helm install -f helm.yaml traefik traefik/traefik --create-namespace -n traefik