---
layout: page
title: "Nello Lock"
description: "Instructions on how to integrate Nello intercom devices."
date: 2017-08-13 17:25
sidebar: true
comments: false
sharing: true
footer: true
logo: nello.png
ha_category: Lock
featured: false

ha_release: 0.52
ha_iot_class: "Cloud Polling"
---

The `nello` platform allows you to control [Nello](https://nello.io) intercoms.

To get started you need to create a secondary Nello account and authorize it to access your lock(s).

<p class="note warning">
Be aware that if you use your main account for Home Assistant you may not be able to use it with the App.
</p>

## {% linkable_title Configuration %}

To add your Nello locks to your installation, add the following to your `configuration.yaml` file:

```yaml
# Example configuration.yaml entry
lock:
  - platform: nello
    username: YOUR_USERNAME
    password: YOUR_PASSWORD
```

{% configuration %}
username:
  description: The username of your Nello account.
  required: true
  type: string
password:
  description: The password of your Nello account.
  required: true
  type: string
{% endconfiguration %}

## {% linkable_title Events %}

### {% linkable_title Event `nello_bell_ring` %}

Every time someone rings the bell, a `nello_bell_ring` event will be fired.

Field | Description
----- | -----------
`address` | Postal address of the lock.
`date` | Date when the event occurred.
`description` | Human readable string describing the event.
`location_id` | Nello ID of the location where the bell has been rung.
`short_id` | Shorter Nello ID.
