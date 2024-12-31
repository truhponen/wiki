---
title: 'Access to applications'
date: '08:08 31-12-2024'
taxonomy:
    category:
        - docs
routes:
    default: /access-to-applications
---

All [applications](/user-applications) have subdomains that can be used from internet and [home network](/lan). This enhances usability as you don't need to remember IPs and ports.

Central part of solution is [HAproxy](/haproxy) that forwards subdomain traffic to different [user applications](/user-applications). Some [infra applications](/infra-applications) also have domains.

Traffic from internet goes through [Cloudflare](/cloudflare) to [HAproxy](/haproxy).

Traffic inside [home network](/lan) is managed by [Technitium DNS](/technitium-dns). It acts mainly as recursive DNS but for kotimme.cc domain it acts as an authoritive DNS and directs traffic to [HAproxy](/haproxy).