---
title: 'Light automation'
date: '23:47 21-12-2024'
routes:
    default: /light-automation
taxonomy:
    category:
        - docs
---

Light automation controls brightness of [lights](/lights). Light automation is managed by [Home Assistant](/home-assistant).

1. [Light sensor](/sensors) monitors external lightness
2. [Sensor](/sensors) sends information over [Zigbee network](/zigbee-network) to [Zigbee2MQTT](/zigbee2mqtt)
3. [Zigbee2MQTT](/zigbee2mqtt) send information to [Home Assistant](/home-assistant) through [Mosquitto](/mosquitto)
4. [Light control](/light-control) calculates preferred brightness and adjusts brightness of [lights](/lights).