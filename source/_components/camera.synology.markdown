---
layout: page
title: "Synology Surveillance Station IP Camera"
description: "Instructions how to integrate Synolog Surveillance Station cameras within Home Assistant."
date: 2016-10-13 13:49
sidebar: true
comments: false
sharing: true
footer: true
logo: synology.png
ha_category: Camera
---

　
The `synology` platform allows you to watch the live streams of your [Synology](https://www.synology.com/) Surveillance Station based IP cameras in Home Assistant.

To enable your Surveillance Station cameras in your installation, add the following to your `configuration.yaml` file:

```yaml
# Minimum configuration.yaml entry
camera:
  - platform: synology
    url: SYNOLOGY_URL
    username: USERNAME
    password: PASSWORD
```

Configuration variables:

- **url** (*Required*): The url to your synology, including port.
- **username** (*Required*): The username for accessing surveillance station.
- **password** (*Required*): The password for accessing surveillance station.
- **whitelist** (*Optional*): A list of which cameras you want to add, the names must be the same as in Surveillance Station.  If omited all cameras are added.
- **verify_ssl** (*Optional*): True to require a valid certificate, False to disable certificate checking.

A full sample configuration for the `synology` platform is shown below:

```yaml
# Example configuration.yaml entry
camera:
  - platform: synology
    url: https://192.168.1.120:5001
    username: USERNAME
    password: PASSWORD
    verify_ssl: False
```

<p class='note'>
Most users will need to set valid_ssl to false unless they have installed a valid SSL certificate in place of the built in self signed certificate.
</p>
