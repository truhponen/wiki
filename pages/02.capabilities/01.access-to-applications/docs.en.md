---
title: 'Access to applications'
date: '08:08 31-12-2024'
taxonomy:
    category:
        - docs
routes:
    default: /access-to-applications
---

All [user applications](/user-applications) and some [infra applications](/infra-applications) have subdomains that can be used from internet and [home network](/lan). This enhances usability as you don't need to remember IPs and ports.

Central part of solution is [HAproxy](/haproxy) that forwards traffic to different [user applications](/user-applications) and [infra applications](/infra-applications).

If user is in public internet, authoritative DNS for kotimme.cc-domain is [Cloudflare](/cloudflare) that forwards traffic through [Cloudflare tunnel](/cloudflare) to [HAproxy](/haproxy). Also, if user is using [Cloudflare Warp-client](/cloudflare) traffic goes the same route.

If user is in [home network](/lan), authoritative DNS for kotimme.cc-domain is [Technitium DNS](/technitium-dns) that forwards traffic straight to [HAproxy](/haproxy).