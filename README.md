# AI Diet Chatbot 🍉🍇

**AI Diet Chatbot** is a lightweight Python-based conversational assistant that helps users with diet and nutrition guidance by combining a language model with a simple chat history store. The project includes a minimal web API and example code to run locally and deploy to a cloud host.

---

## 🪜 Table of Contents

- Project Overview
- Features
- Repository Structure
- Requirements
- Installation
- Configuration
- Running Locally
- Deployment
- Security and Secrets
- Suggested Improvements
- Contributing
- License
- Contact

---

## 🌄 Project Overview

This repository implements a small web service that accepts chat requests, maintains conversation history, and forwards prompts to a language model pipeline. It is intended as a starting point for building a diet-focused conversational assistant and for experimenting with model-driven chat flows.

---

## 🔑 Features

- **Conversational API** for diet and nutrition questions  
- **Persistent chat history** stored in MongoDB  
- **Pluggable LLM pipeline** (abstracted in code as `llm` / `chain`)  
- **Simple JSON API endpoints** for chat and health checks  
- **Ready for deployment** to cloud platforms such as Render

---

## 🪜 Repository Structure

**Top-level files**

- **`main.py`** — Application entry point and API routes.  
- **`requirements.txt`** — Python dependencies.  
- **`README.md`** — Project documentation.  
- **`LICENSE`** — Apache-2.0 license.

**Key code elements in `main.py`**

- **`ChatRequest`** — request model for incoming chat messages.  
- **`get_history`** — helper to fetch conversation history from MongoDB.  
- **`/`** — home or health-check endpoint.  
- **`/chat`** — main chat endpoint that accepts user input, builds a prompt, calls the LLM chain, and stores responses.

---

## 🔐 Requirements

- **Python 3.10+** (or compatible)  
- **MongoDB** instance (Atlas or self-hosted)  
- **An LLM provider or local model runtime** compatible with the code’s `llm`/`chain` abstraction  
- **Optional**: Render account for deployment

---

## 🧑‍🏫 Installation

```bash
# create and activate virtual environment
python -m venv venv
source venv/bin/activate   # macOS / Linux
venv\Scripts\activate      # Windows

# install dependencies
pip install -r requirements.txt
```
---

## 📃  Configuration
Create a .env file or set environment variables required by the app. The code references the following environment variables:

- GROQ_API_KEY — API key for the model provider (if applicable)

- MONGO_URI — MongoDB connection string

- PORT — Port to run the web server on (default commonly 8000 or 5000)

- Any other provider-specific keys used by your LLM integration

### Example .env

- GROQ_API_KEY=<YOUR_GROQ_API_KEY>
- MONGO_URI=<YOUR_MONGODB_URI>
- PORT=8000

---

## 🏃‍♂️‍➡️ Running Locally

```bash
# ensure env vars are set
export GROQ_API_KEY="..."
export MONGO_URI="mongodb+srv://user:pass@cluster.example.mongodb.net/dbname"

# run the app
python main.py
```


Open http://localhost:8000 for the health check and POST to /chat with JSON payloads matching the ChatRequest model.

---
## Example request
```bash
{
  "user_id": "user123",
  "question": "What should I eat for a low-carb dinner?"
}
```
---
## ✈️ Deployment
- This project is deployable to Render and similar PaaS providers.

- 🌐 Live model URL:-  [ LIVE WEBAPP URL](https://ai-diet-chatbot.onrender.com/docs#/default/chat_chat_post)  
- Try the live model 👆

---


## 🛜 Contributing
Contributions are welcome. Suggested workflow:

1. Fork the repository.

2. Create a feature branch.

3. Add tests and documentation for your changes.

4. Open a pull request describing the change.

Please follow the repository’s code style and include tests for new behavior.

---
## 📃 License
- This project is licensed under the Apache License 2.0.
---

---

## 👤 Author

Name: **Ashish Raj**

📌 - GitHub: [Github Profile](https://github.com/ashishraj-hub)

📌 - LinkedIn: [Linkedin Profile](https://www.linkedin.com/in/ashish-raj-ashishraj/)

---
## 📬 Contact

If you have feedback, suggestions, or collaboration ideas, feel free to connect on LinkedIn.

---

## ⭐ Support This Project

If this README or project helped you:
- **Star** ⭐ this repository
- **Fork** 🍴 it and build your own version
- **Share** it with someone who is learning Data Science or AI/ML

---
