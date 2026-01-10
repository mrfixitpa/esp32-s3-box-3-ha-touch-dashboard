# ESP32-S3-Box-3 Custom Voice Assistant Display

This repository contains a **custom ESPHome package** for the **ESP32-S3-Box-3**, designed for use as a **Home Assistant Voice Assistant satellite** with a **stable, clean idle display and touch-friendly UI**.

The goal of this project is to provide a **clean, minimal, and informative display** by removing unnecessary UI elements, improving stability, and presenting useful, always-visible information when the device is idle.

> ✅ **Current Stable Release:**  
> The features described below are part of the **v0.1.6 stable release**.

---

## ✨ Features

### 🧼 Clean Display Layout
- Removes the default **top and bottom text boxes (bubbles)**
- Uses **full-screen custom illustrations** for all voice assistant states
- Clean, distraction-free interface designed for wall or desk placement
- Dark blue idle background for improved contrast and reduced glare

---

### 🕒 Idle Screen (Clock, Temperature & HVAC Status)
When the voice assistant is idle, the display shows:
- A **large, centered digital clock**
- **Indoor temperature** pulled directly from Home Assistant
- **HVAC system status icon**
  - 🔥 Heating (red, fixed)
  - ❄️ Cooling (blue, fixed)
  - Hidden when idle or unavailable
- Optional **AM/PM indicator** (12-hour mode only)

> The clock colon is **static** (no blinking) to reduce redraw load and improve long-term stability.

The display automatically returns to this screen after voice interactions complete.

---

### 🎨 UI Theme Color Picker
The ESP32-S3-Box-3 exposes a **virtual RGB light** in Home Assistant that provides a **full color wheel UI**.

- The selected color is applied to:
  - Clock text
  - AM / PM indicator
  - Indoor temperature text
- Color selection is **stored on the device** and restored after reboot
- HVAC icons are **not affected** by the theme color

> This feature is implemented **entirely in ESPHome** — no Home Assistant helpers or templates are required.

---

### 🎛 Clock Controls (No Reflash Required)
After flashing, Home Assistant exposes configuration controls:
- 12-hour / 24-hour time format toggle
- AM/PM display toggle (12-hour mode only)
- AM/PM **horizontal offset slider**
- AM/PM **vertical offset slider**

> **Behavior note:**  
> When 24-hour mode is enabled, the AM/PM indicator is automatically disabled.

All changes apply instantly and do **not** require recompiling firmware.

---

### 🎙️ Voice Assistant Integration
When you say **“Hey Jarvis”**, the display seamlessly switches to full-screen illustrations that reflect the current state:

- **Listening**
- **Thinking**
- **Speaking / Replying**
- **Error / Not Ready**
- **Timer Finished**

Once the response is complete, the display returns to the idle clock screen.

---

## 📁 Configuration File

> ⚠️ **Important:**  
> This repository provides an **ESPHome package file**, not a complete standalone device configuration.  
> It must be **included in your main ESP32-S3-Box-3 ESPHome YAML** and requires light editing before compiling.

### `box3-ha-touchdash.yaml`
Includes:
- Bubble-free display layout
- Idle clock with temperature
- HVAC heating/cooling indicator (thermostat-agnostic)
- UI theme color picker
- Full voice assistant state illustrations
- User-adjustable clock and AM/PM settings
- Debounced redraw logic for long-term stability

---

## 🚀 Quick Start Guide

### Requirements
- ESP32-S3-Box-3
- Home Assistant
- ESPHome installed in Home Assistant
- **Any Home Assistant temperature sensor**
- **Any Home Assistant climate (thermostat) entity** that exposes `hvac_action`

---

### Step 1: Add the Package to ESPHome
In your **main ESPHome device YAML**, add:

```yaml
packages:
  s3_box_touchdash:
    url: github://mrfixitpa/esp32-s3-box-3-ha-touch-dashboard/box3-ha-touchdash.yaml@v0.1.6
```

---

### Step 2: Edit Before Compiling

#### 1️⃣ Define your indoor temperature sensor
```yaml
sensor:
  - platform: homeassistant
    id: avg_indoor_temp
    entity_id: sensor.average_indoor_temperature
    internal: true
```

---

#### 2️⃣ Define your thermostat (HVAC status)
```yaml
text_sensor:
  - platform: homeassistant
    id: hvac_action
    entity_id: climate.your_thermostat
    attribute: hvac_action
    internal: true
```

---

### Step 3: Compile and Upload
- Click **Install**
- Upload firmware to the ESP32-S3-Box-3
- Wait for the device to reboot

---

## 🛠 Notes & Tips

- Screen dimming is best handled using Home Assistant automations.
- Avoid fast `interval:` redraw loops; the package uses event-driven redraws for stability.
- Designed for readability from across a room and for 24/7 uptime.

---

## 📄 License
Provided as-is for personal and educational use.
