---
title: 'Track temperature'
date: '19:47 21-12-2024'
---

# Temperature tracking

Temperature tracking is process that transfers temperature information from sensors to Home Assistant and other applications.

1. Temperature is tracked with various which send information with 433 MHz radio.
2. Information sent by sensors is captured with [https://lilygo.cc/products/lora3](Lilygo LoRa32 V2.1_1.6) which runs Open MQTT Gateway
3. Open MQTT Gateway send information by wlan to Mosquitto MQTT server
4. Mosquitto publishes information to Home Assistant and Influx DB
5. Home Assistant stores information to sensors which are displayed on frontend
6. Influx DB uses Telegraf agent to read information to Influx DB