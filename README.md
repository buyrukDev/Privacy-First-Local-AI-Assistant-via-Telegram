# 🤖 Privacy-First Local AI Assistant via Telegram
<div align="center">

![Banner](https://capsule-render.vercel.app/api?type=waving&color=auto&height=300&section=header&text=Local%20AI%20Assistant&fontSize=90)


[![n8n](https://img.shields.io/badge/n8n-Workflow_Automation-FF6584?style=for-the-badge&logo=n8n)](https://n8n.io)
[![Ollama](https://img.shields.io/badge/Ollama-Local_LLM-white?style=for-the-badge&logo=ollama&logoColor=black)](https://ollama.com)
[![Docker](https://img.shields.io/badge/Docker-Containerization-2496ED?style=for-the-badge&logo=docker)](https://www.docker.com/)
[![Telegram](https://img.shields.io/badge/Telegram-Bot_API-2CA5E0?style=for-the-badge&logo=telegram)](https://telegram.org)

**A fully local, privacy-focused AI assistant running on Docker, orchestrated by n8n, and accessible via Telegram.**
</div>

---

## 📖 About The Project

This project demonstrates how to build a **sovereign AI assistant** that runs entirely on your local machine. Unlike cloud-based solutions, **no data leaves your server**. 

It uses **Ollama** to run the **Gemma 3 (12b)** model locally and **n8n** to manage the logic flow between the user (Telegram) and the AI.

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
    User[User] -- Telegram --> TgAPI["Telegram API"]
    TgAPI -- "Webhook (ngrok)" --> n8n["n8n (Orchestrator)"]
    n8n -- HTTP Request --> Ollama["Ollama (Gemma 3:12B)"]
    Ollama -- Response --> n8n
    n8n -- Response --> User
```
---

## 🛠️ Tech Stack

* **Orchestration:** [n8n](https://n8n.io) (Self-hosted)
* **AI Runner:** [Ollama](https://ollama.com)
* **LLM Model:** Gemma 3:12b (or Llama 3)
* **Interface:** Telegram Bot API
* **Deployment:** Docker & Docker Compose
* **Tunneling:** ngrok (for Webhook exposure)

---

## 🚀 Getting Started

Follow these steps to run the project on your local machine.

### Prerequisites
* Docker & Docker Compose installed
* Ollama installed and running (`ollama run gemma3:12b`)
* A Telegram Bot Token (via @BotFather)

### Installation

1.  **Clone the repository**
    ```bash
    git clone https://github.com/Mur-ti/Privacy-First-Local-AI-Assistant-via-Telegram.git
    cd Privacy-First-Local-AI-Assistant-via-Telegram
    ```

2.  **Configure Environment**
    Edit the `docker-compose.yml` file to include your ngrok URL or domain.

3.  **Run with Docker**
    ```bash
    docker compose up -d
    ```

4.  **Import Workflow**
    * Open n8n at `http://localhost:5678`
    * Create a new workflow
    * Import the `.json` file provided in this repo.
    * Add your **Telegram Credentials** and verify **Ollama Host** settings.

---

## 📸 Screenshots

<div align="center">
  <img src="https://github.com/user-attachments/assets/57d4bb1c-ce3d-43f7-bc69-8e087c63f6a9" alt="n8n Workflow" width="100%"/>
  <br>
  <em>Figure 1: n8n Workflow Logic</em>
</div>
<br>
<div align="center">
  <img width="771" height="1059" alt="Telegram Screenshot" src="https://github.com/user-attachments/assets/4659cad4-881b-4dc0-92b0-057f414d4158" />
  <br>
  <em>Figure 2: A working example</em>
</div>

---

## 🤝 Contact

**Murtaza** - [GitHub Profile](https://github.com/buyrukDev)

Project Link: [https://github.com/Mur-ti/Privacy-First-Local-AI-Assistant-via-Telegram](https://github.com/Mur-ti/Privacy-First-Local-AI-Assistant-via-Telegram)
