---
title: Portainer
taxonomy:
    category:
        - docs
---

# Installation / update
Portainer documentation https://docs.portainer.io/start/install-ce/server/docker/linux#deployment

1. Create network

       docker network create \
         --driver=bridge \
         --subnet=172.20.0.0/16 \
         --ip-range=172.20.0.0/24 \
         --gateway=172.20.0.1 \
         default-network

2. Stop current Portainer

       docker stop portainer

3. Remove current Portainer 

       docker rm portainer

4. Pull latest image

       docker pull portainer/portainer-ce:latest

5. Run Portainer. Command maps certificates from mounted directory to Portainer default files

       docker run -d -p 8000:8000 -p 9000:9000 -p 9443:9443 \
       --name portainer --restart=always --network=default-network \
       -v /config/cert/certificate.pem:/certs/portainer.crt -v /config/cert/key.pem:/certs/portainer.key \
       -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce:latest

# Common issues

* Bad Gateway from Cloudflare to Portainer is due to fact that Portainer container is not in same network with Cloudflared.

* Startup fails due to conflict with port 8000

      docker run -d -p 9000:9000 -p 9443:9443 \
      --name portainer --restart=always --network=default-network \
      -v /config/cert/certificate.pem:/certs/portainer.crt -v /config/cert/key.pem:/certs/portainer.key \
      -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce:latest