---
title: Cloudflared
date: '14:09 02-01-2025'
taxonomy:
    category:
        - docs
routes:
    default: /cloudflared
---

Cloudflared-application is used for [accessing home network](/access-to-applications) from public internet.

Cloudflared-application is the private end of [Cloudflare-tunnel](/cloudflare). Public end is in [Cloudflare-cloud infrastructure](/cloudflare).

Cloudflared-application runs in [Docker](/docker) and it's in the same [Docker-network](/docker-network) with [HAProxy](/haproxy).