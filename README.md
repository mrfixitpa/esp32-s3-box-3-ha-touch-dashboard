# ESP32-S3-Box-3 HA Touch Dashboard

A custom ESPHome configuration for the **ESP32-S3-BOX-3** that keeps the Voice Assistant experience intact while providing a clean, glanceable **idle dashboard** with **Home Assistant touch buttons**.

## Idle Screen
- **Background illustration** (hosted PNGs in this repo)
- **Indoor temp** text in the top-left
- **HVAC status icon** in the top-right (flame for heating, snowflake for cooling)
- Large centered **clock** with **date**
- 3 always-tappable **light buttons** along the bottom:
  - Living Room: `light.living_room_can_lights` (mdi:sofa-outline)
  - Dining Room: `light.dining_room_light` (mdi:table-chair)
  - Kitchen: `light.kitchen_lights` (mdi:chef-hat)

### Button visuals
- **OFF:** icon + ring match the clock color for easy glanceability
- **ON:** high-contrast **amber** ring + icon

## Voice Assistant
Wake words and assistant states (listening/thinking/replying/error) still take over the screen. When finished, the device returns to the custom idle screen.

## Quick Start
1. Copy the YAML into ESPHome.
2. Update entity IDs in `substitutions:` to match your Home Assistant setup.
3. Validate, compile, and install.

## Assets
Illustrations are hosted in:
- `assets/illustrations/`

## Releases
See `CHANGELOG.md` for release history.
