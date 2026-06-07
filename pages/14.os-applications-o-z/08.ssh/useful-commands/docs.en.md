---
title: 'Useful commands'
date: '19:41 04-02-2025'
taxonomy:
    category:
        - docs
---

Generate private-public key pair

    ssh-keygen -t ed25519 -C "[comment here]"
    
 Copy public key to remote
 
    ssh-copy-id -i ~/.ssh/ansible.pub 192.168.68.50