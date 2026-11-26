# DustBoy NC28 web flasher

Flash the DustBoy NC28 firmware (LCDWIKI / Freenove ES3C28P, 2.8" ESP32-S3) from Chrome or Edge
over USB. One HTML file: React (esm.sh + htm), Tailwind (browser build) and
[ESP Web Tools](https://esphome.github.io/esp-web-tools/).

**Open:** https://laris-co.github.io/dustboy-nc28-flasher/

## What is in this repo

- `index.html` — the flasher page
- `fw/manifest-<device>.json` + `fw/<device>.factory.bin` — ESPHome factory images (offset 0)
- `fw/devices.json` — the device list the page offers

## Bootstrap image, no secrets

The images here are **bootstrap** builds: no MQTT password, no OTA password, no API encryption
key (each image is scanned for every fleet secret before it is published). The screen, Wi-Fi
setup and sensors work; data is not sent. Once the board is on Wi-Fi, the DustBoy team installs
the real firmware over OTA.

Firmware source is not in this repo. Images are built from the private firmware tree with
`PUBLIC=1 ./build.sh <id>`.

## After flashing

1. The top-right pill counts down while waiting for Wi-Fi.
2. Tap **⚙ NC-xxx** → pick Wi-Fi → password → **Join**; the screen shows each step.
3. If nothing is set in time, the board opens a hotspot and the pill blinks **AP**.
