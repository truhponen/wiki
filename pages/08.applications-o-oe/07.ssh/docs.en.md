---
title: SSH
date: '20:52 22-12-2024'
taxonomy:
    category:
        - docs
---

Generate private-public key pair

    ssh-keygen -t ed25519 -C "[comment here]"
    
 Copy public key to remote
 
    ssh-copy-id -i ~/.ssh/ansible.pub 192.168.68.50