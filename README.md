# 🛡️ LLM Guardrails Application

A demo web application built with **FastAPI + Google Gemini** that demonstrates **input and output guardrails** for safer LLM interactions.

![Python](https://img.shields.io/badge/Python-3.x-blue)
![FastAPI](https://img.shields.io/badge/FastAPI-009688)
![Google Gemini](https://img.shields.io/badge/LLM-Google%20Gemini-4285F4)

## 🔍 Overview

Every user prompt passes through a 4-stage security pipeline:

```text
User Prompt
     ↓
🛡️ Input Guardrail
     ↓
🤖 Gemini Generation
     ↓
🔒 Output Guardrail
     ↓
✅ Final Response
```

### 🛡️ Input Guardrail

Checks for:

* 🚫 Blocked keywords
* 🧩 Prompt injection
* 🔓 Jailbreak patterns
* 📏 Empty or oversized prompts

### 🔒 Output Guardrail

Checks Gemini responses for:

* 🔑 API keys
* 🔐 Passwords and secrets
* ⚠️ Empty responses

## 🛠️ Tech Stack

* 🐍 **Python / FastAPI**
* 🤖 **Google Gemini**
* 🌐 **HTML / CSS / JavaScript**
* 📦 **Pydantic / Uvicorn**
* 🔧 **python-dotenv**

## 📁 Project Structure

```text
├── app.py
├── config.py
├── guardrails.py
├── output_guardrails.py
├── gemini_service.py
├── requirements.txt
├── templates/
│   └── index.html
└── static/
    ├── script.js
    └── style.css
```

## 🚀 Setup

```bash
python -m venv venv
pip install -r requirements.txt
```

Create `.env`:

```env
GEMINI_API_KEY=your-api-key
GEMINI_MODEL=your-model-name
```

Run:

```bash
uvicorn app:app --reload
```

Open **http://127.0.0.1:8000**

## 🔗 API Endpoints

| Method | Endpoint    | Purpose                 |
| ------ | ----------- | ----------------------- |
| `GET`  | `/`         | 🌐 Web interface        |
| `GET`  | `/health`   | ❤️ Health check         |
| `POST` | `/generate` | 🤖 Guarded LLM response |

## 🔐 Security Note

Never commit `.env` or API keys to GitHub. This project is an **educational demonstration** of LLM guardrails, not a complete production security solution.
