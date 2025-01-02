---
title: 'SSH from outside of home network'
date: '22:36 31-12-2024'
taxonomy:
    category:
        - docs
routes:
    default: /ssh-from-outside-of-home-network
---

There is multiple ways to SSH to servers.

When device has [Cloudlare](/cloudflare) Warp-connections active. Internal IP addresses can be reached from device and you can use any terminal application.

[Cloudlare](/cloudflare) provides also "SSH browser rendering". In practice there is subdomains (ssh...kotimme.cc) for each backend systems. After logging into [Cloudlare](/cloudflare) it is possible to login to https://wiki.kotimme.cc/en/computers.
[Cloudlare](/cloudflare) provides also "SSH browser rendering". In practice there is subdomains (ssh...kotimme.cc) for each backend systems. After logging into [Cloudlare](/cloudflare) it is possible to login to [servers]() and [LXCs](https://wiki.kotimme.cc/en/lxc).

**External sources**
* [https://developers.cloudflare.com/cloudflare-one/connections/connect-devices/warp/](https://developers.cloudflare.com/cloudflare-one/connections/connect-devices/warp/)
* [https://developers.cloudflare.com/cloudflare-one/connections/connect-networks/use-cases/ssh/ssh-browser-rendering/](https://developers.cloudflare.com/cloudflare-one/connections/connect-networks/use-cases/ssh/ssh-browser-rendering/)