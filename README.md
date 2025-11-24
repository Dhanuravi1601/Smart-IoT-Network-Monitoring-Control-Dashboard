# Smart-IoT-Network-Monitoring-Control-Dashboard
The Smart IoT Network Monitoring &amp; Control Dashboard is a full-stack system designed to simulate IoT devices using multiple protocols (MQTT, CoAP, HTTP/WebSocket), collect telemetry and network metrics, and visualize device status and network topology on a React dashboard. 
The Smart IoT Network Dashboard provides a unified interface to:

View real-time telemetry from IoT devices

Monitor device status, connectivity, and alerts

Control devices remotely (commands, toggles, configurations)

Store & analyze historical data

Visualize insights with charts, logs, and maps

This project includes:

IoT Device Layer (real or simulated)

Edge Gateway / Protocol Translator

Message Broker (MQTT / CoAP / HTTP ingress)

Backend API + Real-Time Server

React Dashboard Frontend

Databases (Telemetry + Metadata)

DevOps + CI/CD Support

🧰 Technologies Used
Devices / Simulation

Python (asyncio, paho-mqtt, aiocoap)

C/C++ or MicroPython (optional for real hardware)

Messaging Layer

EMQX or Mosquitto (MQTT Broker)

Optional: RabbitMQ / Kafka for scaling

Backend

Node.js + TypeScript

NestJS or Fastify

Socket.IO or Native WebSockets for live updates

MQTT.js / CoAP libraries

Databases

InfluxDB — Telemetry

PostgreSQL — Device metadata, users

Redis — Caching

Frontend

React + TypeScript

Redux Toolkit / Zustand for state

Recharts / Chart.js

Tailwind CSS / Chakra UI

Leaflet / Mapbox for device location

DevOps

Docker & docker-compose

GitHub Actions

Prometheus + Grafana

ELK / Loki for logs

🏗️ System Architecture
 ┌──────────────────────────────────────────────┐
 │                  IoT Devices                 │
 │ (MQTT / CoAP / HTTP, Python/C++ Simulator)   │
 └──────────────────────────┬───────────────────┘
                            │
                    (Secure TLS/mTLS)
                            │
 ┌──────────────────────────────────────────────┐
 │               Protocol Gateway               │
 │   MQTT <→> CoAP <→> HTTP Normalizer (Node)   │
 └──────────────────────────┬───────────────────┘
                            │
                    Publish / Subscribe
                            │
 ┌──────────────────────────────────────────────┐
 │                 Message Broker               │
 │            EMQX / Mosquitto / Kafka          │
 └──────────────────────────┬───────────────────┘
                            │
                   Stream Processing
                            │
 ┌───────────────┬────────────────┬──────────────┐
 │ Telemetry DB  │  Backend API   │ Real-time WS │
 │  InfluxDB     │  NestJS/TS     │  Socket.IO   │
 └───────────────┴────────────────┴──────────────┘
                            │
                      REST + WebSocket
                            │
 ┌──────────────────────────────────────────────┐
 │               React Frontend UI              │
 │   Live Charts • Maps • Controls • Alerts     │
 └──────────────────────────────────────────────┘

✨ Features
✔ Real-Time Device Monitoring

Live graphs (temperature, humidity, voltage, etc.)

Device health, connectivity, online/offline status

✔ Multi-Protocol Support

MQTT

CoAP

HTTP / WebSockets

✔ Control Devices

Send commands

OTA configuration update

Toggle/trigger remote actions

✔ Data Storage

High-volume telemetry ingestion

Historical analytics

Downsampling & retention policies

✔ Security

TLS/mTLS communication

JWT authentication

Role-based access

✔ DevOps Support

Dockerized architecture

GitHub Actions CI

Observable system (logs + metrics)

📁 Project Structure
/iot-dashboard
│
├── backend/                 # Node.js + TypeScript backend
│   ├── src/
│   ├── controllers/
│   ├── services/
│   ├── websockets/
│   ├── mqtt-client/
│   └── ...
│
├── frontend/                # React + TypeScript dashboard
│   ├── src/
│   ├── components/
│   ├── hooks/
│   ├── charts/
│   └── ...
│
├── device-simulator/        # Python MQTT/CoAP device emulator
│   ├── mqtt_device.py
│   ├── coap_device.py
│   └── ...
│
├── docker-compose.yml       # Dev environment
└── README.md
