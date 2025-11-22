# 👁️ Project IRIS

![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Nvidia](https://img.shields.io/badge/Nvidia_CUDA-76B900?style=for-the-badge&logo=nvidia&logoColor=white)
![Ollama](https://img.shields.io/badge/Ollama-Backend-black?style=for-the-badge)
[![License](https://img.shields.io/github/license/Cluyverth/Project-IRIS?style=for-the-badge)](LICENSE)

**Project IRIS** is a robust, containerized ecosystem for running Large Language Models (LLMs) locally and privately. 

It orchestrates a high-performance AI stack using **Docker Compose**, bridging the **Ollama** inference engine with modern, user-friendly web interfaces, fully optimized for **Nvidia GPU acceleration**.

## 🏗️ The Stack

Project IRIS connects three powerful components in an isolated network (`iris-network`):

1.  **🧠 Ollama (Backend):** The engine that runs the models (Llama 3, Mistral, Gemma, etc.). Configured for full Nvidia GPU passthrough.
2.  **💬 Lobe Chat (UI 1):** A modern, high-performance chatbot interface with plugin support and a clean design. accessible at port `3210`.
3.  **🌐 Open WebUI (UI 2):** A feature-rich interface (formerly Ollama WebUI) offering advanced chat history, RAG (Retrieval Augmented Generation), and model management. Accessible at port `3211`.

## 🚀 Prerequisites

- **Docker** & **Docker Compose** installed.
- **Nvidia GPU** (Optional but recommended).
- **Nvidia Container Toolkit** installed (Required for the GPU configuration in `docker-compose.yml`).

## 🛠️ Installation & Usage

### 1. Clone the repository
```bash
git clone https://github.com/Cluyverth/Project-IRIS.git
cd Project-IRIS
```

### 2. Start the Ecosystem
Run the stack in detached mode:

```bash
docker compose up -d
```

### 3. Access the Interfaces

| Service | URL | Description |
| :--- | :--- | :--- |
| **Lobe Chat** | `http://localhost:3210` | Modern, aesthetic chat interface. |
| **Open WebUI** | `http://localhost:3211` | Advanced UI with RAG and management features. |
| **Ollama API** | `http://localhost:11434` | Direct API access. |

## 🧠 Managing Models

Since the Ollama container starts empty, you need to pull a model first. You can do this via the **Open WebUI** interface or the command line:

```bash
# Example: Pulling Llama 3 inside the container
docker compose exec ollama ollama run llama3
```

## 📂 Project Structure

```bash
.
├── docker-compose.yml   # Orchestration logic
├── .gitignore           # Ignores Python caches & personal docs
├── .dockerignore        # Optimizes build context
└── PersonalDocsFolder/  # (Ignored) Place for local RAG documents/scripts
```

## 🐍 Python Development

This project is set up for Python development/scripting (e.g., for custom RAG pipelines or automation). The `.gitignore` is configured to keep your environment clean by ignoring `__pycache__`, `.venv`, and `.env` files.
