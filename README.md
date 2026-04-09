# 🚀 TS API Demo (Dockerized)

## 📌 Overview

A simple REST API built with **TypeScript** and **Express**, designed to demonstrate Docker best practices using both:

* 🐳 Single-stage Docker build
* 🏗️ Multi-stage Docker build (optimized for production)

The project also includes a health check endpoint and runs as a non-root user in production for better security.

---
## 📥 Clone Repository

```bash
git clone https://github.com/Hisham-Mizeed/Multistage-Dockerfile-Task.git
cd Multistage-Dockerfile-Task

## 🎯 Features

* ⚡ Fast TypeScript-based API
* 🐳 Docker support (single & multi-stage)
* 🔒 Runs as non-root user (multi-stage)
* ❤️ Health check endpoint (`/health`)
* 👤 System identity endpoint (`/whoami`)

---

## 🛠️ Tech Stack

* Node.js 20
* TypeScript
* Express.js
* Docker

---

## 📂 Project Structure

```
.
├── src/
│   └── index.ts
├── Dockerfile.single    # Single-stage build
├── Dockerfile.multistage# Multi-stage optimized build
├── package.json
└── tsconfig.json
```

---

## ⚙️ Installation (Local)

1. Install dependencies:

```bash
npm install
```

2. Run in development:

```bash
npm run dev
```

---

## 🧪 API Endpoints

### ❤️ Health Check

```
GET /health
```

Response:

```json
{
  "ok": true,
  "service": "TS API"
}
```

---

### 👤 Who Am I

```
GET /whoami
```

Response:

```json
{
  "uid": 1000,
  "gid": 1000
}
```

---

## 🐳 Docker Usage

### 🔹 Single-stage Build

Build image:

```bash
docker build -f Dockerfile.single -t ts-api-single .
```

Run container:

```bash
docker run -p 3000:3000 ts-api-single
```

---

### 🔹 Multi-stage Build (Recommended ✅)

Build image:

```bash
docker build -f Dockerfile.multistage -t ts-api .
```

Run container:

```bash
docker run -p 3000:3000 ts-api
```

---

## 🔍 Health Check (Docker)

The multi-stage image includes a built-in health check:

* Endpoint: `/health`
* Interval: 30s
* Retries: 3

---

## 🌍 Environment Variables

| Variable | Default | Description      |
| -------- | ------- | ---------------- |
| PORT     | 3000    | Server port      |
| APP_NAME | TS API  | Application name |

Example:

```bash
docker run -p 3000:3000 -e APP_NAME="My API" ts-api
```

---

## 📌 Future Improvements

* Add logging system (Winston / Pino)
* Add request validation
* Add Docker Compose
* Add CI/CD pipeline

---

## 👨‍💻 Author

Hisham Ahmed

---

## 📄 License

This project is open-source and available under the MIT License.
