[README.md](https://github.com/user-attachments/files/23842230/README.md)
# 🤖 Privacy-First Local AI Assistant via Telegram

![Banner](https://capsule-render.vercel.app/api?type=waving&color=auto&height=300&section=header&text=Local%20AI%20Assistant&fontSize=90)

<div align="center">

[![n8n](https://img.shields.io/badge/n8n-Workflow_Automation-FF6584?style=for-the-badge&logo=n8n)](https://n8n.io)
[![Ollama](https://img.shields.io/badge/Ollama-Local_LLM-white?style=for-the-badge&logo=ollama&logoColor=black)](https://ollama.com)
[![Docker](https://img.shields.io/badge/Docker-Containerization-2496ED?style=for-the-badge&logo=docker)](https://www.docker.com/)
[![Telegram](https://img.shields.io/badge/Telegram-Bot_API-2CA5E0?style=for-the-badge&logo=telegram)](https://telegram.org)

**A fully local, privacy-focused AI assistant running on Docker, orchestrated by n8n, and accessible via Telegram.**
</div>

---

## 📖 About The Project

This project demonstrates how to build a **sovereign AI assistant** that runs entirely on your local machine. Unlike ChatGPT or Claude, **no data leaves your server**. 

It uses **Ollama** to run the **Gemma 2 (12b)** model locally and **n8n** to manage the logic flow between the user (Telegram) and the AI.

### 🌟 Key Features
* **🔒 100% Privacy:** All chat data stays on your local machine.
* **⚡ Local Inference:** Powered by Google's Gemma model via Ollama.
* **🤖 Smart Automation:** Workflow logic handled by n8n.
* **📱 Instant Access:** Accessible directly from Telegram Mobile/Desktop.
* **🐳 Dockerized:** Easy deployment with a single `docker-compose` file.

---

## 🏗️ Architecture

```mermaid
graph LR
    A[User 📱] -- Telegram --> B(Telegram Bot API)
    B -- Webhook --> C[n8n Workflow ⚡]
    C -- Local Network --> D[Ollama 🦙]
    D -- Inference --> C
    C -- Response --> B
    B -- Message --> A
