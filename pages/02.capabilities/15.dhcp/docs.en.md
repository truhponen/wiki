---
title: DHCP
date: '07:38 20-01-2025'
taxonomy:
    category:
        - docs
---

DHCP is handled by [LAN router](/lan).

When in Devices in home's LAN, they should use [internal Technitium DNS](/technitium-dns) as primary DNS. This eases [accessing applications](/access-to-applications) by skipping [Cloudflare](/cloudflare) authentication and speeds up DNS resolution.

Currently Deco router is handling DHCP but doesn't seem to offer DHCP for IPv6 network. So, there is no easy way to distribute local IPv6 nameserver to devices in network. [Technitium DNS](/technitium-dns) could also act as a DHCP server but it neither offers DHCPv6.

**External sources**
* [https://en.wikipedia.org/wiki/DHCPv6](https://en.wikipedia.org/wiki/DHCPv6)
* [https://www.reddit.com/r/technitium/comments/opegwf/dhcp_and_ipv6/](https://www.reddit.com/r/technitium/comments/opegwf/dhcp_and_ipv6/)