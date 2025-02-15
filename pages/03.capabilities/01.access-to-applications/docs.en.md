---
title: 'Access to applications'
date: '08:08 31-12-2024'
taxonomy:
    category:
        - docs
routes:
    default: /access-to-applications
---

Most of [container applications](/container-applications) have [subdomains](/domains) that can be used from internet and [home network](/lan). This enhances usability as you don't need to remember IPs and ports. Also Cloudflare's [SSH browser rendering](/ssh-from-outside-of-home-network) has own [subdomains](/domains).

Central part of solution is [HAproxy](/haproxy) that forwards traffic to different [container applications](/container-applications). Traffic related to Cloudflare's [SSH browser rendering](/ssh-from-outside-of-home-network) doesn't go to [HAproxy](/haproxy).

If [user](/users) is in public internet or using [Cloudflare Warp-client](/cloudflare).... 
1. authoritative DNS for kotimme.cc-domain is [Cloudflare DNS](/cloudflare)
2. DNS directs traffic to [Cloudflare tunnel](/cloudflare) ("CNAME IN <tunnel_UUID>.cfargotunnel.com")
3. tunnel leads to [Cloudflared-application](/cloudflared) running in [Docker container](/docker)
4. [Cloudflared-application](/cloudflared) directs traffic to [HAproxy](/haproxy) that is running in same [Docker network](/docker).
5. [HAproxy](/haproxy) resolves correct backend based on it's configurations.
 

If [user](/users) is in [home network](/lan)...
1. authoritative DNS for kotimme.cc-domain is [Technitium DNS](/technitium-dns)
2. [Technitium DNS](/technitium-dns) has conditional forwarder zone which specifies A records for all subdomains except Cloudflare's [SSH browser rendering](/ssh-from-outside-of-home-network) subdomains.
3. [Technitium DNS](/technitium-dns) forwards traffic straight to [HAproxy](/haproxy). [SSH domain](/ssh-from-outside-of-home-network) requests are forwarded to Cloudflare DNS
4. [HAproxy](/haproxy) resolves correct backend based on it's configurations.


**External sources**
* [https://developers.cloudflare.com/cloudflare-one/connections/connect-networks/routing-to-tunnel/dns/](https://developers.cloudflare.com/cloudflare-one/connections/connect-networks/routing-to-tunnel/dns/)
* [https://developers.cloudflare.com/cloudflare-one/connections/connect-devices/warp/](https://developers.cloudflare.com/cloudflare-one/connections/connect-devices/warp/)