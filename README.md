# ESP32-S3-Box-3 HA Touch Dashboard

An ESPHome configuration for the **ESP32-S3-Box-3** that provides a clean idle dashboard for Home Assistant:

- **Top strip:** Indoor Temperature + HVAC status
- **Center:** Large clock + date
- **Bottom:** 3 always-tappable touch buttons that toggle Home Assistant lights

The voice assistant UI (wake word / listening / thinking / replying) still takes over as normal, and the device returns to this idle screen when done.

---

## Features

### Idle Screen
- Custom `idle.png` background (320×240)
- Large clock + day/date
- Indoor Temperature text + value (from Home Assistant)
- HVAC action icon (heating/cooling) from your climate entity

### Touch Buttons (Always Tappable)
Bottom row buttons toggle these Home Assistant entities:

- Living Room: `light.living_room_can_lights` (mdi:sofa-outline)
- Dining Room: `light.dining_room_light` (mdi:table-chair)
- Kitchen: `light.kitchen_lights` (mdi:chef-hat)

**Visual behavior**
- Off = grey
- On = bright cyan + glow (“pop” visibility)

### On-device Adjustments
- **Clock Horizontal Offset**: slider in Home Assistant to nudge the clock left/right.

---

## Requirements
- Home Assistant + ESPHome
- ESP32-S3-Box-3
- Entities in Home Assistant:
  - `light.living_room_can_lights`
  - `light.dining_room_light`
  - `light.kitchen_lights`
  - `climate.*` entity exposing `hvac_action`
  - Indoor temperature sensor entity

---

## Quick Start
1. Copy the YAML into ESPHome.
2. Confirm/adjust the entity IDs (lights, climate, indoor temp).
3. Compile + install to the ESP32-S3-Box-3.
4. Add the device to Home Assistant.

---

## Versioning
Releases use semantic versioning (`v0.x.y`) while the project is still evolving.

