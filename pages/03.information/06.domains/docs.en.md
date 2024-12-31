---
title: Domains
date: '23:14 31-12-2024'
taxonomy:
    category:
        - docs
routes:
    default: /domains
---

Domains are managed in three different places and used in various places.

Cloudflare DNS has configurations related to @-, *- and ssh-domains. @ and * traffic  is forwarded through tunnel to HAProxy and ssh-traffic is forwarded to respective resource. *-domain is used to make Cloudflare configuration simple.

Technitium DNS has configuration related to "@" and all "non-ssh"-domains, and it forwards their traffic to HAProxy. SSH traffic needs to go to Cloudflare as it provides SSH in browser feature.

HAProxy has configuration related to "@" and all "non-ssh"-domains, and it forwards their traffic to correct backends.

There is URLs related to domains in various user applications - most of them are in Home Assistant and Homepage.