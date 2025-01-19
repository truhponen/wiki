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

Currently only IPv4 network is enabled. This is due to DHCP configurations. Devices in home's LAN should use [internal Technitium DNS](/technitium-dns) as primary DNS. This eases [accessing applications](/access-to-applications) by skipping Cloudflare authentication and speeds up DNS resolution. Currently Deco router is handling DHCP but doesn't seem to offer DHCP for IPv6 network. So, there is no easy way to distribute local IPv6 nameserver to devices in network. [Technitium DNS](/technitium-dns) could also act as a DHCP server but it neither offers DHCPv6.

**External sources**
* [https://en.wikipedia.org/wiki/DHCPv6](https://en.wikipedia.org/wiki/DHCPv6)
* [https://www.reddit.com/r/technitium/comments/opegwf/dhcp_and_ipv6/](https://www.reddit.com/r/technitium/comments/opegwf/dhcp_and_ipv6/)