# esp8266 rc-switch to mqtt gateway

Based on libraries:

PubSubClient https://github.com/knolleary/pubsubclient

RC-Switch https://github.com/sui77/rc-switch

![Hardware image](./rc-switch_to_mqtt_gate_hardware.jpg)

Radio module Telecontrolli RR10 http://www.telecontrolli.com/catalogue/product/rr10.html

Home assistant integration example:
```
automation:
  - alias: Togle bedroom light
    initial_state: True
    hide_entity: False
    trigger:
      platform: mqtt
      topic: "rcswitch/value"
      payload: "2314567"
    action:
      service: light.toggle
      entity_id: "light.bedroom"

```

