# 🎧 Video to Audio Converter Microservices App on Kubernetes

This project is a fully containerized microservices application that allows users to upload a video file, convert it to audio (MP3), and download the result. The system is built with Python microservices and deployed on Kubernetes, incorporating JWT authentication, asynchronous task queues, cloud-native storage, and notification systems.

---

## 📌 Features

- 🔐 JWT Authentication and secure login
- 🎥 Upload video files
- 🎶 Asynchronous audio (MP3) extraction using `ffmpeg`
- ☁️ Store binary media data in MongoDB
- 📩 Push and email notifications on conversion completion
- 🚀 Deployed using Kubernetes (Minikube/GKE)
- 🐇 Uses RabbitMQ for video/audio processing queue
- 📦 Microservices-based architecture using Docker and Python (FastAPI)

---

## 🛠️ Tech Stack

| Layer               | Tech                          |
|--------------------|-------------------------------|
| API Framework      | Python (FastAPI)              |
| Auth & Data Store  | PostgreSQL, JWT               |
| Queuing System     | RabbitMQ                      |
| Storage            | MongoDB (for binary MP3 files)|
| Notifications      | SMTP (email), Push API        |
| Containerization   | Docker                        |
| Orchestration      | Kubernetes + Helm             |
| CI/CD (optional)   | GitHub Actions / Jenkins      |

---


---

## 🧩 Microservices Overview

| Service        | Description                                       |
|----------------|---------------------------------------------------|
| `/login`       | Authenticates user and issues JWT                 |
| `/upload`      | Accepts video upload, pushes to RabbitMQ queue    |
| `Converter`    | Listens to video queue, extracts MP3 via `ffmpeg` |
| `/download`    | Allows user to download the converted audio       |
| `Notification` | Sends push and email notifications post-conversion|

---

## 🚀 Getting Started

### Prerequisites

- Python 3.9+
- Docker
- Kubernetes (Minikube or GKE)
- Helm (optional)
- `kubectl` CLI
- RabbitMQ (Dockerized or external)
- MongoDB & PostgreSQL instances (or use Docker Compose)

