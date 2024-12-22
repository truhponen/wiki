---
title: 'Light control'
date: '10:55 22-12-2024'
taxonomy:
    category:
        - docs
routes:
    default: /light-control
---

Light control has two sides:
1. Events that trigger adjustments to lights
2. Adjustments of lights.
[Home Assistant](/home-assistant) automations "tie" these sides together.

## Trigger events

Trigger event can come from multiple sources:
* [sensors](/sensors)
* [schedules](/schedules)
* physical [buttons](/buttons)
* virtual buttons in Home Assistant UI
Route of event is different depending on source but all events become [events](/events) in Home Assistant.

### Adjustment of lights

There is custom python script that is used to adjust lights. Script adds abstraction level to light adjustments. Behavior of script can be controlled with variables, such as "start brightness", "end brightness" and "transition time". Python script could be replaced with regular Home Assistant script.

Events have different types of predefined variables. This way each even can be easily configured to produce different type of light adjustment.

The actual light adjustment is conducted by Home Assistant. There is different types of [lights](/lights) and therefore different types of light integrations.
