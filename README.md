# Tater S3 Box Display (ESPHome)

A clean, always-on Home Assistant display for the **ESP32-S3 Box**, built with **ESPHome**.

This config shows:
- Large **time** and **full weekday date**
- **Indoor & outdoor temperature** with **humidity**
- A rotating **weather icon + value** (wind, rain rate, lightning)
- Warm orange accents matched to the original S3 Box look

Everything is rendered locally on the device and pulls live data from Home Assistant sensors.

---

## Features

- 🕒 Big, readable clock
- 📅 Full weekday date (Friday, not Fri)
- 🌡️ Indoor / Outdoor temperature
- 💧 Indoor / Outdoor humidity (smaller text)
- 🌬️ Rotating weather icon:
  - Wind speed
  - Rain rate
  - Lightning strikes
- 🎨 Black / white / orange color scheme
- 💡 Backlight always on (configurable)
![IMG_0178-ezgif com-resize](https://github.com/user-attachments/assets/9c4b1395-4962-4266-a3be-a287958e7bf1)

---

## Requirements

- ESP32-S3 Box (ILI9XXX display)
- ESPHome `2024.12.2` or newer
- Home Assistant with the following sensors (or equivalents):
  - Outdoor temperature
  - Indoor temperature
  - Wind speed
  - Rain rate
  - Lightning strikes
  - Indoor humidity
  - Outdoor humidity

---

## Setup

1. Copy the YAML into a new ESPHome device.
2. Update the **sensor entity IDs** at the top:
   ```yaml
   substitutions:
     sensor_temp_out: sensor.weather_outdoor_temperature
     sensor_temp_in: sensor.living_room_temperature
     sensor_humidity_out: sensor.weather_outdoor_humidity
     sensor_humidity_in: sensor.living_room_humidity
   ```

## Icons

This display uses **Material Design Icons (MDI)** loaded from a remote font file.

Icon codes used in this config:

- **Wind:** `F059E`
- **Rain:** `F0597`
- **Lightning:** `F0593`

You can browse and search for more icons here:
https://pictogrammers.com/library/mdi/

When changing icons, update:
- The glyph list in the `font:` section
- The icon codes in the display `lambda`

---

## Notes

- Fonts and icons are loaded directly from GitHub (no local files required)
- Layout and spacing are tuned specifically for the ESP32-S3 Box display
- Designed to stay simple, fast, and always readable
