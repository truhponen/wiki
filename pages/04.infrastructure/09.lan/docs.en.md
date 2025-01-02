---
title: LAN
date: '21:23 21-12-2024'
taxonomy:
    category:
        - docs
routes:
    default: /lan
---

Our home's local area network consists:

* TP-link Deco mesh routers
* ZyXEL GS-105B and GS-108B v3 switches

Currently onli IPv4 is enabled. This is due to DHCP configurations. Devices in home's LAN should use [internal DNS](/technitium-dns) as primary DNS as this eases [accessing applications](https://wiki.kotimme.cc/en/access-to-applications) by skipping Cloudflare authentication and [speeds up DNS resolution](https://wiki.kotimme.cc/en/technitium-dns). Deco routers don't seem to offer DHCP for IPv6 network, so there is no easy way to distribute local IPv6 nameserver to devices in network.

[Technitium DNS](/technitium-dns) could also act as a DHCP server and might solve the issue but currently there is no plans to implement it.