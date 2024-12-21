---
title: NGINX
taxonomy:
    category:
        - docs
child_type: docs
routes:
    default: /nginx
---

> <pre><code>events {}
> http {
>     server {
>         listen 80;
>         listen [::]:80;
>     
>         server_name truhponen.duckdns.org;
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
> #        server_name truhponen.duckdns.org;
> #    
> #        ssl_certificate /etc/nginx/ssl/live/truhponen.duckdns.org/fullchain.pem;
> #        ssl_certificate_key /etc/nginx/ssl/live/truhponen.duckdns.org/privkey.pem;
> #        
> #        location / {
> #        	# ...
> #        }
> #    }
> }</code></pre>