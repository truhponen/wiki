---
title: DHCP
date: '07:38 20-01-2025'
taxonomy:
    category:
        - docs
routes:
    default: /dhcp
---

DHCP is handled by [LAN router](/lan).

When in device in [home LAN](/lan), DHCP defines [internal Technitium DNS](/technitium-dns) as primary DNS. This eases [accessing applications](/access-to-applications) by skipping [Cloudflare](/cloudflare) authentication and speeds up DNS resolution.

Currenly [home LAN](/lan) uses IPv4 and router doesn't offer DHCP for IPv6 network. [Technitium DNS](/technitium-dns) could also act as a DHCP server but it neither offers DHCPv6. At the moment there is no easy way to distribute local IPv6 nameserver to devices in network.

**External sources**
* [https://en.wikipedia.org/wiki/DHCPv6](https://en.wikipedia.org/wiki/DHCPv6)
* [https://www.reddit.com/r/technitium/comments/opegwf/dhcp_and_ipv6/](https://www.reddit.com/r/technitium/comments/opegwf/dhcp_and_ipv6/)