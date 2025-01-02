---
title: Domains
date: '23:14 31-12-2024'
taxonomy:
    category:
        - docs
routes:
    default: /domains
---

Domains enhance usability of home network as you don't need to remember IPs and ports. All [user applications](/user-applications) and many [infra applications](/infra-applications) have dedicated subdomains. Also [Cloudflare's SSH browser rendering feature](/ssh-from-outside-of-home-network) has subdomains. 

Domain related information is managed in four different places and used in various places.

[Cloudflare DNS](/cloudflare) has DNS records for...
* @-, and "non-ssh..."-domains which are related to [accessing applications](/access-to-applications)
* ssh...-domains which are related to [ssh-traffic](/ssh-from-outside-of-home-network)

[Technitium DNS](/technitium-dns) has DNS records for...
* @- and "non-ssh..."-domains which are related to [accessing applications](/access-to-applications)
* request related to other subdomains (i.e. ssh...-domains) are forwarded to [Cloudflare DNS](/cloudflare)

[HAProxy](/haproxy) has backend configurations for...
* @- and "non-ssh"-domains which are related to [accessing applications](/access-to-applications)

[Cloudflare tunnels](/cloudflare) have backend configurations for...
* ssh...-domains which are related to [ssh-traffic](/ssh-from-outside-of-home-network)