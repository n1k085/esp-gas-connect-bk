# ESP Gas Connect BK

ESPHome firmware for the **ESP Gas Connect BK** by [NG3D](https://ng3d-druck.de/products/reedkontakt-sensor-bk-gaszaehler-esp32):
a reed contact pulse sensor for BK gas meters with a built-in Waveshare ESP32-C3-Zero.

## Hardware

| Pin    | Function                          |
| ------ | --------------------------------- |
| GPIO4  | Reed contact (to GND, pull-up)    |
| GPIO10 | Onboard WS2812 RGB LED            |

One revolution of the last drum digit of a BK meter equals 0.01 m³, so each pulse counts 0.01 m³.

## Entities

- **Gas meter reading** (m³, `total_increasing`, device class `gas`) - for the Home Assistant energy dashboard
- **Gas flow** (m³/h)
- **Set meter reading** - enter the value shown on your meter once, it is persisted across reboots
- **Reed contact** (diagnostic) - live contact state, useful when aligning the sensor
- **LED**, **Restart**, **WiFi signal**, **Uptime**, **Firmware** update

## Setup

1. Power the device via USB-C.
2. Connect it to your Wi-Fi with Improv via Bluetooth (Home Assistant / ESPHome app),
   Improv via USB at the [web installer](https://n1k085.github.io/esp-gas-connect-bk/), or the fallback hotspot.
3. Adopt it in Home Assistant and set **Set meter reading** to the current value of your meter.

## Files

- `esp-gas-connect-bk.yaml` - the configuration you get when taking control in the ESPHome Device Builder
- `esp-gas-connect-bk.factory.yaml` - the factory firmware (adds Improv, project info and OTA updates)
