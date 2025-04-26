# LumiNode Project

LumiNode is a modular, WiFi-enabled IoT platform built around the Arduino MKR1000.  
It enables smart control of WS2812B LED strips and SPI TFT displays, combined with a scalable server application for device management and monitoring.  
Designed for seamless integration into Home Automation Systems (HAS) and Industry 4.0 environments.

---

## 📂 Project Structure

```plaintext
luminode/
├── README.md                  # Main project documentation
├── led_node/                   # Firmware for LumiNode devices
│   ├── README.md
│   ├── src/
│   ├── include/
│   ├── lib/
│   └── platformio.ini
├── server_app/                 # Server application (ElectronJS)
│   ├── README.md
│   ├── src/
│   ├── public/
│   ├── package.json
│   └── electron.config.js
└── docs/                       # Additional documentation (optional)
```

---

## 🚀 Components

### led_node (Firmware)
- Developed in C++ using PlatformIO (Arduino Framework)
- WiFi client operation via WiFi101 Library
- WebSocket and MQTT communication
- Control WS2812B LEDs and a TFT display
- Local settings persistence (FlashStorage)
- Modular and extensible with sensors and input devices

### server_app (ElectronJS Application)
- ElectronJS-based desktop application
- Manages multiple LumiNode devices
- Real-time status monitoring
- Control LEDs and display settings
- Modular dashboard design
- Prepared for OTA firmware update management

---

## 🛠️ Requirements

- **Hardware**
  - Arduino MKR1000 board
  - WS2812B LED strip (or compatible NeoPixel)
  - 1.28" TFT SPI display
  - Stable 5V USB power supply

- **Software**
  - [PlatformIO](https://platformio.org/) (for led_node firmware development)
  - [Node.js](https://nodejs.org/) (for server_app)

---

## 📚 Documentation

- [led_node/README.md](./led_node/README.md) – Detailed documentation for the Node firmware
- [server_app/README.md](./server_app/README.md) – Server application documentation

Additional specifications and system design details can be found in the `docs/` directory.

---

## 📈 Roadmap Highlights

- OTA firmware updates (server-controlled)
- Sensor data collection and analysis (temperature, humidity, motion)
- Dashboard enhancements (device grouping, visual analytics)
- Full Home Assistant integration via MQTT auto-discovery

---

## 📜 License

This project is licensed under the MIT License.  
See the [LICENSE](./LICENSE) file for details.

---

> **LumiNode** connects smart lighting, visual feedback, and real-time management – wireless, modular, and ready for the future.
```