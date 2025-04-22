# LumiNode – WiFi-based Smart LED & TFT Display Controller for Home Automation

**LumiNode** is an ESP32-based smart controller designed to manage a WS2812B LED strip and a 1.28" SPI TFT display over WiFi. It communicates via MQTT and WebSocket, making it ideal for integration into modern Home Automation Systems (HAS).

---

## 🔧 Features

- Control of a 60-LED WS2812B strip with customizable effects
- Continuous display of an analog clock and temperature on TFT
- WiFi client mode with static configuration
- MQTT for all control commands
- Optional WebSocket interface for configuration
- NTP time synchronization
- Designed for integration with Home Assistant or Node-RED
- Fully modular and easy to expand with sensors or input devices

---

## ⚙️ Hardware Overview

| Component        | Description                            |
|------------------|----------------------------------------|
| ESP32-WROOM-32   | WiFi-enabled microcontroller            |
| WS2812B LED Strip| 60 individually addressable RGB LEDs   |
| 1.28" TFT Display| SPI interface, driver 50318            |
| Power Supply     | 5V USB power supply (up to 10A)        |

### GPIO Pin Configuration

| Function     | GPIO | Note                                |
|--------------|------|-------------------------------------|
| LED Data     | 5    | WS2812B data line                   |
| TFT MOSI     | 23   | SPI MOSI                            |
| TFT SCK      | 18   | SPI Clock                           |
| TFT CS       | 15   | Chip Select                         |
| TFT DC       | 2    | Data/Command                        |
| TFT RESET    | 4    | Display reset pin                   |

---

## 📶 Communication

### MQTT Topics

| Topic                     | Payload Example           | Description                      |
|---------------------------|---------------------------|----------------------------------|
| `luminode/led/mode`       | `solid`, `rainbow`, etc.  | LED animation mode               |
| `luminode/led/color`      | `#FF0000`                 | HEX RGB color                    |
| `luminode/led/brightness` | `0-255`                   | LED brightness level             |
| `luminode/display/time`   | ISO string or `auto`      | Time update (optional)           |

### WebSocket

- Used for runtime configuration (e.g., WiFi/MQTT credentials)
- Activated only when needed

---

## 🖥️ Display Features

- Always-on analog clock
- Temperature reading (via external sensor, e.g., DHT22)
- Display powered by [TFT_eSPI](https://github.com/Bodmer/TFT_eSPI)

---

## ⏱️ Time Synchronization

- NTP server: `pool.ntp.org`
- Timezone example (Switzerland):
```cpp
configTime("CET-1CEST,M3.5.0,M10.5.0/3", "pool.ntp.org");
```

---

## 📚 Libraries Used

- [FastLED](https://github.com/FastLED/FastLED)
- [TFT_eSPI](https://github.com/Bodmer/TFT_eSPI)
- [PubSubClient](https://github.com/knolleary/pubsubclient)
- [ESPAsyncWebServer](https://github.com/me-no-dev/ESPAsyncWebServer) *(optional)*

---

## 🔐 Security

- No authentication required
- No HTTPS (local network use only)
- No persistent configuration storage (no SPIFFS/LittleFS)

---

## 🧩 Extensions

- Add sensors (temperature, humidity, etc.)
- Add physical buttons (e.g. for mode switching)
- Integrate into Home Assistant using MQTT Discovery
- Optional: OTA firmware updates

---

## 🚀 Getting Started

1. Connect your ESP32 via USB
2. Open project in PlatformIO or Arduino IDE
3. Define WiFi and MQTT credentials in code
4. Flash the firmware to the ESP32
5. Start controlling LEDs and display via MQTT!

---

> **LumiNode** brings ambient lighting and visual feedback together – wirelessly, efficiently, and tailor-made for your smart home setup.
