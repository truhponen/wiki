---
title: Zigbee2MQTT
date: '23:52 21-12-2024'
taxonomy:
    category:
        - docs
routes:
    default: /zigbee2mqtt
---

Zigbee2MQTT is bridge software that is central part of [Zigbee network](/zigbee-network) and it works in tandem with physical [Zigbee coordinator](/zigbee-coordinator).

Zigbee2MQTT translates Zigbee messages to [MQTT messages](/mqtt-messages) and send them to [Mosquitto](/mosquitto) MQTT server that publishes it to different solutions, e.g. [Home Assistant](/homme-assistant) and [Telegraf](/telegraf).