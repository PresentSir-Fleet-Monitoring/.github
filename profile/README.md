# 🚌 PresentSir: Distributed Real-Time Telemetry & Fleet Intelligence
![Docker](https://img.shields.io/badge/Docker-Enabled-blue?logo=docker&logoColor=white)
![Render](https://img.shields.io/badge/Backend-Render_Cloud-46E3B7?logo=render&logoColor=white)
![Supabase](https://img.shields.io/badge/Database-Supabase-3ECF8E?logo=supabase&logoColor=white)
![Cloudflare](https://img.shields.io/badge/Frontend-Cloudflare_Pages-F38020?logo=cloudflare&logoColor=white)
![Health](https://img.shields.io/badge/System_Health-Operational-brightgreen)


**PresentSir** is a high-availability telemetry platform. It bridges the gap between physical transit fleets and digital monitoring by utilizing a **Reactive Microservices Architecture**. This ensures seamless, sub-second location synchronization even under aggressive mobile OS power constraints.

---

## 🔗 Live Ecosystem Links
| Resource | Link | Description | GitHub Repository |
| :--- | :--- | :--- | :--- |
| **🌐 Web Dashboard** | [ait-runner.pages.dev](https://ait-runner.pages.dev) | Live Fleet Monitoring (Cloudflare) | [presentsir-web-dashboard](https://github.com/PresentSir-Fleet-Monitoring/presentsir-web-dashboard) |
| **📲 Android App** | [Download APK (v1.0)](#) | GPS Telemetry Client (Android) | [presentsir-mobile-client-android](https://github.com/PresentSir-Fleet-Monitoring/presentsir-mobile-client-android) |
| **📡 Server Health** | [API Status Check](https://presentsir-server.onrender.com/ps/api/public/goodmorning) | Real-time Backend Heartbeat | [presentsir-backend-api](https://github.com/PresentSir-Fleet-Monitoring/presentsir-backend-api) |
| **🏠 Landing Page** | [Official Site](#) | Project Overview & Marketing | [presentsir-landing-page](https://github.com/PresentSir-Fleet-Monitoring/presentsir-landing-page) |

---

## 🏗️ System Architecture & Deployment

### ⚙️ Backend: Spring Boot (Deployed on Render)
The orchestration engine is containerized with **Docker** to ensure environment parity.
* **WebSocket Broker:** Handles full-duplex STOMP traffic.
* **Scalability:** Hosted on Render Cloud with automated CI/CD pipelines.
* **Monitoring:** `/goodmorning` endpoint integrated with Cloudflare Workers for uptime tracking.

### 📱 Mobile: Native Java Engine (Android)
The "Edge" provider designed for extreme reliability.
* **Persistence:** Uses **Foreground Services** to prevent background process termination.
* **Smart Polling:** Fused Location Provider balances GPS precision with battery longevity.

### 🖥️ Frontend: Html/Css/Js (Deployed on Cloudflare)
The administrative Command Center.
* **Edge Delivery:** Assets are served from Cloudflare’s global 250+ PoP locations.
* **Low Latency:** Optimized for sub-500ms marker interpolation.

---

## 🐳 Docker Integration
The backend is fully containerized for scalable deployment:
```bash
# Pull the latest image
docker pull presentsir/backend-server:latest

# Run the orchestration layer
docker run -p 8080:8080 presentsir/backend-server
