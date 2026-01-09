# ESP32-S3-Box-3 Touch Panel (Home Assistant)

A custom ESPHome configuration for the **ESP32-S3-Box-3** that replaces the idle screen with a clean, glanceable UI:
- **Top status strip:** Indoor temperature + HVAC status
- **Center:** Large clock + day/date
- **Bottom:** 3 always-tappable Home Assistant light buttons with state-based styling

Voice assistant behavior is preserved: when the device enters a voice state (wake word / listening / thinking / replying), the assistant UI takes over — and returns to this idle screen when done.

---

## Features

### Idle Screen UI
- Large centered clock + day/date
- Compact top strip for:
  - Indoor temperature (from Home Assistant)
  - HVAC action/icon (from Home Assistant climate entity)

### 3 Home Assistant Touch Buttons
Bottom-row buttons toggle these entities:
- Living Room: `light.living_room_can_lights` (icon: `mdi:sofa-outline`)
- Dining Room: `light.dining_room_light` (icon: `mdi:table-chair`)
- Kitchen: `light.kitchen_lights` (icon: `mdi:chef-hat`)

**Visual behavior**
- Off = greyed out
- On = cyan icon + cyan “glow” effect

### Background
The idle background is an image that can be hosted (e.g., GitHub/HA local) and built into the firmware via ESPHome’s `image:` component.

---

## Requirements
- Home Assistant + ESPHome
- ESP32-S3-Box-3
- Home Assistant entities available:
  - `light.living_room_can_lights`
  - `light.dining_room_light`
  - `light.kitchen_lights`
  - A `climate.*` entity providing `hvac_action`
  - An indoor temperature sensor entity

---

## Quick Start
1. Copy `esp32-s3-box-3-touch-panel.yaml` into your ESPHome config folder.
2. Update the entity IDs at the top of the YAML (lights, climate, indoor temp) to match your Home Assistant setup.
3. Compile + install to the ESP32-S3-Box-3.
4. Add the device to Home Assistant.

---

## Customization
Common tweaks:
- Swap which entities the 3 buttons control
- Change the ON “glow” color
- Replace the idle background image
- Adjust clock/date sizing and layout

---

## Screenshots
Coming Soon

---

## License
Choose a license that matches your intent (MIT is common for configs like this).
