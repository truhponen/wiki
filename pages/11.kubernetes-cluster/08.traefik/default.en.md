---
title: Traefik
date: '20:45 27-02-2025'
---

With default chart

    helm install traefik traefik/traefik --create-namespace -n traefik

With cutomizations

    helm install -f helm.yaml traefik traefik/traefik --create-namespace -n traefik