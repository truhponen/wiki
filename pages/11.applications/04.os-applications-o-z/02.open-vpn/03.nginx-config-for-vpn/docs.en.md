---
title: 'NGINX config for VPN'
date: '20:44 22-12-2024'
taxonomy:
    category:
        - docs
---

    http {
        server {
            listen 80;
            listen [::]:80;
        
            server_name xxxxxx;
            server_tokens off;
        
            location / {
                return 301 https://$host$request_uri;
            }
        }