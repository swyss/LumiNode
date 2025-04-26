# LumiNode – WiFi-based Smart LED & TFT Display Controller

**LumiNode** is a modular MKR1000-based controller for a WS2812B LED strip and a 1.28" SPI TFT display.  
Designed for modern Home Automation Systems, it communicates via MQTT and optional WebSocket, offering high flexibility for SmartHome and Industry 4.0 applications.

---

## 🔧 Features

- Control a 60-LED WS2812B strip with multiple animation modes  
- Continuous analog clock and temperature display on TFT  
- WiFi client mode with static configuration  
- MQTT interface for LED and display control  
- Optional WebSocket interface for live configuration  
- NTP-based time synchronization  
- Designed for Home Assistant or Node-RED integration  
- Fully modular, easily extendable with sensors or buttons  

---

## ⚙️ Hardware Overview

| Component          | Description                                  |
|--------------------|----------------------------------------------|
| Arduino MKR1000     | WiFi-enabled microcontroller (ATSAMD21 + WiFi101) |
| WS2812B LED Strip   | 60 individually addressable RGB LEDs        |
| 1.28" TFT Display   | SPI interface, driver 50318                  |
| Power Supply        | 5V regulated USB power supply               |

### GPIO Pin Configuration

| Function      | GPIO | Notes                                 |
|---------------|------|---------------------------------------|
| LED Data      | 6    | Data line for WS2812B                 |
| TFT MOSI      | 8    | SPI MOSI line                         |
| TFT SCK       | 9    | SPI Clock line                        |
| TFT CS        | 10   | TFT Chip Select                       |
| TFT DC        | 11   | TFT Data/Command                      |
| TFT RESET     | 12   | TFT Reset pin                         |

> ⚠️ *Please verify the final wiring based on your MKR1000 pinout and your setup.*

---

## 📶 Communication Overview

### MQTT Topics

| Topic                        | Payload Example       | Description                  |
|-------------------------------|------------------------|-------------------------------|
| `luminode/led/mode`           | `solid`, `rainbow`      | Set LED animation mode        |
| `luminode/led/color`          | `#FF0000`               | Set LED color (HEX format)    |
| `luminode/led/brightness`     | `128`                  | Set LED brightness (0-255)    |
| `luminode/display/time`       | ISO 8601 string        | Update displayed time         |

### WebSocket

- Live configuration (WiFi, MQTT settings, color presets)
- Enabled on-demand

---

## 🖥️ Display Features

- Analog clock always visible  
- Temperature reading from optional sensors (e.g., DHT22)  
- Driven by [TFT_eSPI](https://github.com/Bodmer/TFT_eSPI) library  

---

## ⏱️ Time Synchronization

- Using NTP servers (`pool.ntp.org`)
- Example for Switzerland time zone:

```cpp
configTime("CET-1CEST,M3.5.0,M10.5.0/3", "pool.ntp.org");
```

---

## 📚 Libraries Used (PlatformIO)

- [FastLED](https://github.com/FastLED/FastLED)
- [TFT_eSPI](https://github.com/Bodmer/TFT_eSPI)
- [PubSubClient](https://github.com/knolleary/pubsubclient)
- [WiFi101](https://github.com/arduino-libraries/WiFi101)
- [ArduinoOTA](https://github.com/jandrassy/ArduinoOTA) *(optional)*
- [WebSockets](https://github.com/Links2004/arduinoWebSockets) *(optional)*

---

## 🔐 Security

- Local network use only (no authentication, no HTTPS)
- No persistent configuration filesystem (no SPIFFS/LittleFS)

---

## 🧩 Possible Extensions

- Additional sensors (temperature, humidity, motion)
- Physical control buttons
- MQTT auto-discovery (Home Assistant integration)
- OTA updates for firmware management

---

## 🚀 Getting Started

1. Connect your MKR1000 via USB.
2. Open the project in **PlatformIO** (Visual Studio Code).
3. Edit `src/config.h` and `platformio.ini` for your network and MQTT settings.
4. Build and upload the firmware.
5. Start controlling your LumiNode over MQTT or WebSocket!

---

> **LumiNode** brings dynamic lighting and real-time information to your smart home – wireless, modular, and reliable.
```