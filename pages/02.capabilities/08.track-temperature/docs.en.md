---
title: 'Track temperature'
date: '19:47 21-12-2024'
published: true
taxonomy:
    category:
        - docs
routes:
    default: /track-temperature
---

Temperature tracking is process that transfers temperature information from sensors to Home Assistant and other applications.

Temperatures are displayed in [Home Assistant](/home-assistant) UI.

1. Temperature is tracked with weather station [sensors with 433 MHz radio](/sensors-with-433-mhz-radio).
2. Information sent by sensors is captured with [Lilygo LoRa32 V2.1_1.6](https://lilygo.cc/products/lora3) which runs [Open MQTT Gateway](/open-mqtt-gateway)
3. [Open MQTT Gateway](/open-mqtt-gateway) send information by wlan to [Mosquitto](/mosquitto) MQTT server
4. [Mosquitto](/mosquitto) publishes information to  [Home Assistant](/home-assistant) and [Influx DB](/influx-db)
5. [Home Assistant](/home-assistant) stores information to sensors which are displayed on frontend
6. [Influx DB](/influx-db) uses [Telegraf](/telegraf) agent to read information to [Influx DB](/influx-db)