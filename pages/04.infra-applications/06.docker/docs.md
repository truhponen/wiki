---
title: Docker
taxonomy:
    category:
        - docs
child_type: docs
routes:
    default: /docker
---

## Creating container image using Docker

To Docker hub

    docker buildx build -t truhponen/my-departures:latest --platform linux/arm64 --push .
        
To Git hub

    sudo docker buildx build -t ghcr.io/truhponen/my-departures:latest --platform linux/arm64 --push .


- "Docker buildx build" to create Pi + Linux compliant image on Windows
- "-t ghcr.io/truhponen/" to Git hub **OR** "-t truhponen/" to Docker hub
- "my-departures:latest" to add right tag
- "--platform linux/arm64" to make image Pi + Linux compliant
- "--push" image
- "." actions in project folder

## Creating container for PROXMOX

Snippets combined from 
- https://docs.docker.com/engine/install/debian/
- https://docs.portainer.io/start/install-ce/server/docker/linux

1. Create Debian Container. Make it small first.

    * cores: 1

    * memory 1024

    * swap 1024

    * disk 4Gb (you cannot in practice decrease)

2. Add Docker repository

        # Add Docker's official GPG key:
        apt-get update
        apt-get install ca-certificates curl gnupg
        install -m 0755 -d /etc/apt/keyrings
        curl -fsSL https://download.docker.com/linux/debian/gpg | gpg --dearmor -o /etc/apt/keyrings/docker.gpg
        chmod a+r /etc/apt/keyrings/docker.gpg
        
        # Add the repository to Apt sources:
        echo \
          "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/debian \
          "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
          tee /etc/apt/sources.list.d/docker.list > /dev/null
        apt-get update

2. Install Docker

        apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

3. Create Portainer volume

        docker volume create portainer_data

4. Install Portainer container

        docker run -d -p 9000:9000 -p 9443:9443 --name portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce:latest