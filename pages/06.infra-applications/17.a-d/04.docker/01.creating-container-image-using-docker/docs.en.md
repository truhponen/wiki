---
title: 'Creating container image using Docker'
date: '23:25 21-12-2024'
taxonomy:
    category:
        - docs
---

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