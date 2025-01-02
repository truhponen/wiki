---
title: HAProxy
date: '08:05 31-12-2024'
taxonomy:
    category:
        - docs
routes:
    default: /haproxy
---

HAProxy is reverse proxy and load balancer. It has central role when [accessing applications](/access-to-applications).

Currently [HAproxy](/haproxy) is not utilized as load balancer as there is only single backends for each service. Still, [HAproxy](/haproxy) is validating health of backends regularly and reporting those in http://192.168.68.111:8404/.

HAProxy has no open ports to public internet.

**External sources:**
* [https://www.haproxy.com/](https://www.haproxy.com/)
