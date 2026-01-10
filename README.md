# ESP32-S3-Box-3 HA Touch Dashboard

This repository contains a **custom ESPHome package** for the **ESP32-S3-Box-3**, providing a **stable, wall-friendly touch dashboard** tightly integrated with Home Assistant.

This project is **separate from the Voice Assistant display repository** and follows its **own versioning (v0.x.x)**.

> 🚧 **Pre-release Notice**  
> The features described below are part of **v0.2.0-pre1**, a pre-release focused on header layout improvements and added outdoor temperature support.

---

## ✨ Features

### ⚡ Stability First
- Event-driven display redraws (no 1-second redraw loop)
- Debounced redraw requests to prevent UI slowdowns
- Touch input debounced for reliable interaction
- Designed for long-term, always-on wall use

---

### 🕒 Idle Header (v0.2.0)
The top header follows a structured, balanced layout:

```
Indoor Temp    [ HVAC ]    Outdoor Temp
```

- **Indoor Temp** — upper left
- **HVAC Status Icon** — centered  
  - 🔥 Heating → red flame  
  - ❄️ Cooling → blue snowflake  
  - Hidden when idle/off
- **Outdoor Temp** — upper right
- Indoor and outdoor temperatures use the **same font, size, and weight**
- Text color follows the selected UI theme
- HVAC icon colors are **state-driven** and ignore UI theming

---

### 🎨 UI Theme Color
- Exposes a virtual RGB light in Home Assistant
- Theme color applies to clock and temperature text
- HVAC icons are not affected by theme color

---

### 👆 Touch Buttons
- Bottom-row touch areas for Home Assistant actions
- Transparent button backgrounds for a clean wall-mounted look
- Touch handling is debounced for reliability

---

## 📁 Package File

> ⚠️ This repository provides an **ESPHome package**, not a full device configuration.

**Main package file:**
- `box3-ha-touchdash.yaml`

---

## 🚀 Quick Start

```yaml
packages:
  box3_touchdash:
    url: github://mrfixitpa/esp32-s3-box-3-ha-touch-dashboard/box3-ha-touchdash.yaml@v0.2.0-pre1
```

---

## 🛠 Notes
- Screen dimming is best handled via Home Assistant automations
- Avoid fast redraw intervals
- Header layout finalized during v0.2.0 pre-releases

---

## 📄 License
Provided as-is for personal and educational use.
