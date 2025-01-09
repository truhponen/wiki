---
title: Snippets
date: '21:49 08-01-2025'
taxonomy:
    category:
        - docs
---

**Task that reads YAML file to variable**

    - name: Read Docker Compose
      ansible.builtin.include_vars:
        dir: 'vars/'
      tags:
      - read_configurations

**Task that interprets YAML-variable to dict and loops through it**

    - name: Print volumes
      ansible.builtin.debug:
        msg: "{{ item.value.volumes }}"
      loop: "{{ lookup('ansible.builtin.dict', services) }}"
      tags:
      - read_configurations

**Read variables from yaml in vars-folder**

    - name: Read Docker Compose from vars
      ansible.builtin.include_vars:
        dir: 'vars/'
      tags:
      - read_configurations


    - name: Extract volume information to list
      ansible.builtin.set_fact:
        volume_list: |
          {%- set list = namespace(items=[]) -%}
          {%- for item in lookup('ansible.builtin.dict', services) -%}
            {%- for i in item.value.volumes -%}
              {%- set list.items = list.items + [i] -%}
            {%- endfor -%}
          {%- endfor -%}
          {{ list.items }}
      tags:
      - read_configurations


    - name: Print volume-list
      ansible.builtin.debug:
        var: volume_list
      tags:
      - read_configurations