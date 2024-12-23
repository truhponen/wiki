---
title: 'Audio control'
date: '10:55 22-12-2024'
taxonomy:
    category:
        - docs
routes:
    default: /audio-control
---

Audio control allows user to control [audio devices](/audio-devices) with various [buttons](/buttons).

Audio control has two sides:
1. [Events](/events) that trigger adjustments to [audio device](/audio-devices)
2. Adjustments of [audio device](/audio-devices)

[Home Assistant automations](/home-assistant-automations) "tie" these sides together.

## Trigger events

Trigger [event](/events) can come from multiple sources:
* [automations](/automations)
* physical [buttons](/buttons)
* [Home Assistant](/home-assistant) UI

Route of [event](/events) is different depending on source but eventually all [events](/events) become [events](/events) in [Home Assistant](/home-assistant).

### Adjustment of audio device

There is several [Home Assistant automations](/home-assistant-automations) that are used to adjust [audio devices](/audio-devices). [Automations](/home-assistant-automations) add abstraction level to adjustments. Behavior of [automations](/home-assistant-automations) can be controlled with [variables](/variables), such as "start volume", "end volume" and "transition time".

[Events](/events) have different types of predefined [variables](/variables). This way each event can be easily configured to produce different type of [audio device](/audio-devices) adjustment.

The actual adjustment of [audio device](/audio-devices) is conducted by [Home Assistant](/home-assistant) through build in [integrations](/home-assistant-integrations).