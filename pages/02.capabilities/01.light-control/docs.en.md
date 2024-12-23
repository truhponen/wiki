---
title: 'Light control'
date: '10:55 22-12-2024'
taxonomy:
    category:
        - docs
routes:
    default: /light-control
---

Audio control allows controlling [lights](/lights) with various [sensors](/sensors), [buttons](/buttons) and [automations](/automations).

Light control has two sides:
1. [Events](/events) that trigger adjustments to [lights](/lights)
2. Adjustments of [lights](/lights).

Home Assistant [automations](/automations) "tie" these sides together.

## Trigger events

Trigger [event](events) can come from multiple sources:
* [sensors](/sensors)
* [schedules](/schedules)
* physical [buttons](/buttons)
* virtual buttons in [Home Assistant](/home-assistant) UI

Route of [event](/events) is different depending on source but eventually all [events](/events) become [events](/events) in Home Assistant.

### Adjustment of lights

There is [custom python script](home-assistant-python-scripts) that is used to adjust lights. Script adds abstraction level to light adjustments. Behavior of script can be controlled with [variables](/variables), such as "start brightness", "end brightness" and "transition time". Python script could be replaced with regular [Home Assistant script](/home-assistant-scripts).

Events have different types of predefined variables. This way each [event](/events) can be easily configured to produce different type of light adjustment.

The actual light adjustment is conducted by Home Assistant trough build in [integrations](/home-assistant-integrations). As there is different types of [lights](/lights), there is different types of [integrations](/home-assistant-integrations).
