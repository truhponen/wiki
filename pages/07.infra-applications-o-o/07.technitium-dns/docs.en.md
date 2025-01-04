---
title: 'Technitium DNS'
date: '08:03 31-12-2024'
taxonomy:
    category:
        - docs
routes:
    default: /technitium-dns
---

Technitium is DNS-solution for [home network](/lan).

Technitium is mainly used as recursive DNS caching DNS-information and this way speeding up DNS resolution in [home network](/lan).

For kotimme.cc-domain in [home network](/lan) it is also authoritative DNS. In public internet [Cloudflare](/cloudflare) is the authoritative DNS.

Technitium has "conditional forwarding zone" for kotimme.cc. In practice there is A-records for [user and infra application domains](/domains). Other kotimme.cc domains are forwarded to [Cloudflare DNS](cloudflare) with FWD-records. There is also "APP"-record implementing "NODATA"-app in kotimme.cc zone. NODATA-app is used to block HTTPS-records which come as they "leak" DNS resolving to Cloudflare.


**External sources:**
* [https://technitium.com/](https://technitium.com/)