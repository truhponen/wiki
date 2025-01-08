---
title: Snippets
date: '21:49 08-01-2025'
taxonomy:
    category:
        - docs
---

Task that reads YAML file to variable

    - name: Read Docker Compose
      ansible.builtin.include_vars:
        dir: 'vars/'
      tags:
      - read_configurations

Task that interprets YAML-variable to dict and loops through it

    - name: Print volumes
      ansible.builtin.debug:
        msg: "{{ item.value.volumes }}"
      loop: "{{ lookup('ansible.builtin.dict', services) }}"
      tags:
      - read_configurations