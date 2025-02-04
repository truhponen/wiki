---
title: 'SSH from outside of home network'
date: '22:36 31-12-2024'
taxonomy:
    category:
        - docs
routes:
    default: /ssh-from-outside-of-home-network
---

There is two ways to SSH to kotimme.cc infra from outside of home network.

1. When device has [Cloudlare](/cloudflare) Warp-connections active. Internal IP addresses can be reached from device and you can use any terminal application on device.
2. [Cloudlare's](/cloudflare) "SSH browser rendering". In practice there is subdomains (ssh...kotimme.cc) for each backend systems. After logging into [Cloudlare](/cloudflare) it is possible to login to [servers](/computers) and [LXCs](https://wiki.kotimme.cc/en/lxc).
   1. "SSH browser rendering" is supported with [custom web page](/ssh-webpage) which form addresses based on container ID's 

**External sources**
* [https://developers.cloudflare.com/cloudflare-one/connections/connect-devices/warp/](https://developers.cloudflare.com/cloudflare-one/connections/connect-devices/warp/)
* [https://developers.cloudflare.com/cloudflare-one/connections/connect-networks/use-cases/ssh/ssh-browser-rendering/](https://developers.cloudflare.com/cloudflare-one/connections/connect-networks/use-cases/ssh/ssh-browser-rendering/)