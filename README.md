# 🌐 Smart Environmental Monitoring & Remote LED Control using MQTT

<p align="center">
  <img src="images/result1.png" width="400"/>
  <img src="images/result2.png" width="400"/>
</p>

---

## 🚀 Project Overview

This project implements a **real-time IoT system** using the **ESP32 microcontroller** and the **MQTT protocol** to:

- 🌡️ Monitor **temperature and humidity**
- ☁️ Transmit data to the cloud
- 💡 Control devices remotely (LED)

It demonstrates **bidirectional communication** between hardware and cloud using lightweight messaging.

---

## 🧠 Key Concepts Covered

- Internet of Things (IoT)
- MQTT Publish–Subscribe Architecture
- Real-time Data Streaming
- Embedded Systems (ESP32)
- Cloud Communication
- Remote Device Control

---

## 🏗️ System Architecture

```mermaid
graph LR
A[DHT22 Sensor] --> B[ESP32]
B -->|Publish| C[MQTT Broker]
C -->|Subscribe| D[MQTT Client (MQTTx)]
D -->|Command| C
C -->|Subscribe| B
B --> E[LED]
```

---

## ⚙️ Features

### 🌡️ Environmental Monitoring
- Reads **temperature & humidity** using DHT22
- Publishes data every **2 seconds**
- Topics:
  - `/ThinkIOT/temp`
  - `/ThinkIOT/hum`

---

### 💡 Remote LED Control
- Subscribes to:
  - `home/led`
- Commands:
  - `ON` → LED ON
  - `OFF` → LED OFF

---

## 🔌 Hardware Requirements

| Component     | Description            |
|--------------|------------------------|
| ESP32        | Microcontroller        |
| DHT22        | Temp & humidity sensor |
| LED          | Output device          |
| Resistor     | Current limiting       |
| Jumper Wires | Connections            |

---

## 💻 Software Requirements

- Arduino IDE
- MQTT Client (MQTTx)

### Libraries
- WiFi.h
- PubSubClient.h
- DHTesp.h

---

## 🌐 MQTT Configuration

| Parameter | Value                        |
|----------|------------------------------|
| Broker   | test.mosquitto.org / HiveMQ  |
| Port     | 1883                         |
| Protocol | MQTT                         |

---

## 📡 MQTT Topics

| Topic             | Type      | Description        |
|------------------|----------|--------------------|
| /ThinkIOT/temp   | Publish  | Temperature data   |
| /ThinkIOT/hum    | Publish  | Humidity data      |
| home/led         | Subscribe| LED control        |

---

## 📁 Project Structure

```bash
mqtt-iot-esp32-monitoring/
│
├── code/
│   ├── temperature_humidity/
│   │   └── esp32_dht22_mqtt.ino
│   └── led_control/
│       └── esp32_led_mqtt.ino
│
├── docs/
│   └── mqtt_report.pdf
│
├── images/
│   ├── result1.png
│   ├── result2.png
│
└── README.md
```

---

## 🔄 Working Principle

### 📤 Data Flow (Sensor → Cloud)
1. ESP32 connects to Wi-Fi  
2. Reads DHT22 sensor data  
3. Publishes to MQTT broker  
4. Client receives real-time data  

---

### 📥 Control Flow (User → Device)
1. User sends ON/OFF command  
2. Broker forwards message  
3. ESP32 receives command  
4. LED state changes  

---

## 🧪 Results

- ✅ Stable Wi-Fi and MQTT connection  
- ✅ Real-time data publishing  
- ✅ MQTT client received:
  - Temperature: **4.50°C**
  - Humidity: **55.5%**
- ✅ LED controlled remotely  

---

## ⚠️ Challenges

- MQTT reconnection handling  
- Wi-Fi stability  
- Payload formatting  
- Topic synchronization  

---

## 🔧 Future Improvements

- Mobile app integration  
- Dashboard (Node-RED / Grafana)  
- Secure MQTT (TLS/SSL)  
- Cloud integration (AWS IoT)  

---

## 🎯 Applications

- Smart Homes  
- Weather Monitoring  
- Industrial IoT  
- Agriculture  

---

## 👨‍💻 Team

- Charan Mahendaran  
- Aditya Nimbargi  
- Likhith K  

---

## 📜 License

For academic and educational use only.

---

## ⭐ Support

If you like this project:
- Star ⭐ the repo  
- Fork 🍴 it  
- Share 📢 it  

---

## 🔥 Author Note

This project demonstrates the **foundation of IoT systems**, combining embedded hardware with cloud communication.
