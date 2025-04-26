# LumiNode Server Application – Node Management and Dashboard

The **LumiNode Server App** is a modular ElectronJS application to manage, configure, and monitor multiple LumiNode devices within a home or industrial network.  
It provides a real-time dashboard and acts as a bridge between IoT devices and user control interfaces.

---

## 🔧 Features

- Manage multiple LumiNode nodes over WebSocket  
- Real-time node status monitoring  
- Control LED colors, modes, and brightness  
- Visualize system states and sensor data on the dashboard  
- Modular design for easy integration of new features  
- Ready for future OTA firmware update management  

---

## 🖥️ Dashboard Overview

- List all registered LumiNode devices
- Display connection status (Connected / Disconnected / Error)
- Send control commands (e.g., LED color, brightness, animation)
- View current configurations and logs
- Modular extension support (e.g., sensors, statistics, firmware manager)

---

## 📂 Project Structure

```plaintext
server-app/
├── README.md
├── src/
│   ├── main.js                  # Electron main process
│   ├── nodeManager.js            # Manages node connections and states
│   ├── dashboard/                # Frontend components
│   ├── websocket/                # WebSocket server handlers
│   └── utils/                    # Helper functions
├── public/
│   ├── index.html                # Dashboard HTML
│   └── assets/                   # Static files (CSS, images, icons)
├── package.json
└── electron.config.js            # Electron configuration file
```

---

## 🚀 Getting Started

1. Install [Node.js](https://nodejs.org/).
2. Install dependencies:

```bash
cd server-app
npm install
```

3. Start the Electron application:

```bash
npm run start
```

---

## ⚙️ Configuration

- Define listening port and WebSocket parameters in `electron.config.js`.
- Customize dashboard theme and modules inside `src/dashboard/`.

---

## 🔐 Security

- Local network only (LAN operation)  
- Optional access control to be implemented in future releases  

---

## 🧩 Future Roadmap

- OTA firmware update manager
- Device grouping and custom profiles
- Integration with SmartHome platforms (e.g., Home Assistant)

---

> **LumiNode Server** – A powerful management hub for your smart IoT environment.
```

---

# 📄 (optional) Verbesserte `README.md` (Main Project)

Hier eine kleine, verfeinerte Version für Dein Hauptprojekt:

```markdown
# LumiNode Project

LumiNode is a modular, WiFi-enabled IoT platform built around the Arduino MKR1000.  
It provides smart control of WS2812B LED strips and TFT displays, integrated into a scalable management system via an ElectronJS server application.

---

## 📂 Project Structure

```plaintext
luminode/
├── README.md                  # Main project documentation
├── led_node/                   # Firmware for LumiNode device
│   ├── README.md
│   ├── src/
│   ├── include/
│   └── platformio.ini
├── server_app/                 # ElectronJS server application
│   ├── README.md
│   ├── src/
│   ├── public/
│   ├── package.json
│   └── electron.config.js
└── docs/                       # Additional documentation (optional)
```

---

## 🚀 Components

- **led_node**: Firmware for MKR1000 controlling LED and display modules
- **server_app**: Desktop application for management, configuration, and monitoring

---

## 🛠️ Requirements

- Arduino MKR1000 board
- WS2812B LED strip
- 1.28" TFT SPI display
- PlatformIO (for firmware development)
- Node.js + npm/yarn (for server application)

---

## 📚 Documentation

- [led_node/README.md](./led_node/README.md) – Firmware details
- [server_app/README.md](./server_app/README.md) – Server application details

---

## 📜 License

This project is licensed under the MIT License.
```