---
title: 'Light automation'
date: '23:47 21-12-2024'
routes:
    default: /light-automation
taxonomy:
    category:
        - docs
---

Light automation controls brightness of lights. Light automation is managed by [Home Assistant](/home-assistant).

1. [Zigbee light sensor](/zigbee) monitors external lightness
2. Sensor sends information to [Zigbee2MQTT](/zigbee2mqtt)
3. Zigbee2MQTT send information to [Home Assistant](/home-assistant)
4. [Home Assistant](/home-assistant) calculates preferred brightness and adjusts brightness