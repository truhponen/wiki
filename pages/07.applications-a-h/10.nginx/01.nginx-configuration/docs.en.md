---
title: 'Nginx configuration'
date: '09:54 22-12-2024'
taxonomy:
    category:
        - docs
---

> <pre><code>events {}
> http {
>     server {
>         listen 80;
>         listen [::]:80;
>     
>         server_name [public domain];
>         server_tokens off;
>     
>         location /.well-known/acme-challenge/ {
>             root /var/www/certbot;
>         }
>     
>         location / {
>             return 301 https://$host$request_uri;
>         }
>     }
>     
> #    server {
> #        listen 443 default_server ssl http2;
> #        listen [::]:443 ssl http2;
> #    
> #        server_name [public domain];
> #    
> #        ssl_certificate /etc/nginx/ssl/live/[public domain]/fullchain.pem;
> #        ssl_certificate_key /etc/nginx/ssl/live/[public domain]/privkey.pem;
> #        
> #        location / {
> #        	# ...
> #        }
> #    }
> }</code></pre>