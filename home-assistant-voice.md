---
title: Home Assistant Voice
description: 
published: true
date: 2024-12-18T10:41:46.288Z
tags: 
editor: markdown
dateCreated: 2024-12-18T10:41:46.288Z
---

Links to containers from https://www.home-assistant.io/blog/2023/04/27/year-of-the-voice-chapter-2/

# Piper

container image: https://hub.docker.com/r/rhasspy/wyoming-piper

Run

    docker run -it -p 10200:10200 -v /path/to/local/data:/data rhasspy/wyoming-piper --voice en-us-lessac-low

Compose 

    piper:
      image: "rhasspy/wyoming-piper:latest"
          
      restart: unless-stopped
          
      networks:
        home_automation:
        
      ports:
        "10200:10200"
            
      volumes:
        - piper:/data:rw
            
      command: --voice en_US-lessac-medium

# Whisper

container image: https://hub.docker.com/r/rhasspy/wyoming-whisper

Run

    docker run -it -p 10300:10300 -v /path/to/local/data:/data rhasspy/wyoming-whisper --model tiny-int8 --language en

Compose 

    whisper:
      image: "rhasspy/wyoming-whisper:latest"
          
      restart: unless-stopped
          
      networks:
        home_automation:
        
      ports:
        - "10300:10300"
            
      volumes:
        - whisper:/data:rw
            
      command: --model tiny-int8 --language en