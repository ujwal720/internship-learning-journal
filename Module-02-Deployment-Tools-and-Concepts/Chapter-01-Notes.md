# WEEK 2-Session 1 : Containerization with Podman From Basics to a Flask Web App with an LLM Backend

This document provides step-by-step instructions for learning and implementing containerization using Podman, starting from installation and progressing through single-container projects, persistent storage, networking, and finally building a Flask web application backed by a local LLM.

---

## 1. Introduction to Containerization

### What to Do

- Understand containerization as a way to package applications with all dependencies  
- Use containers to avoid OS-specific setup issues  
- Learn the concept of:
  - **Images** (blueprints)
  - **Containers** (running instances)

### Key Idea

A container image includes:

- Application code  
- Runtime (e.g., Python)  
- System dependencies  

---

## 2. Install Podman in WSL

### Update System
```bash
sudo apt update
```

### Install Podman
```bash
sudo apt install -y podman
```

### (Optional) Install QEMU for WSL Compatibility
```bash
sudo apt install -y qemu-system-x86
```

### Verify Installation
```bash
podman --version
```

> **Note:** `podman machine start` may fail in WSL but Podman can still work correctly.

---

## 3. Basic Podman Commands

### Test Podman
```bash
podman run alpine echo "Podman is working"
```

### List Images
```bash
podman images
```

### List Running Containers
```bash
podman ps
```

---

## 4. Project 1: Containerizing Jupyter Lab

### Pull Jupyter Image
```bash
podman pull quay.io/jupyter/base-notebook
```

### Run Jupyter Lab
```bash
podman run -p 8888:8888 quay.io/jupyter/base-notebook
```

### Run in Detached Mode
```bash
podman run -d \
  --name jupyter_lab \
  -p 8888:8888 \
  quay.io/jupyter/base-notebook
```

### View Logs (Get Access Token)
```bash
podman logs jupyter_lab
```

### Access Jupyter
```
http://localhost:8888
```

---

## 5. Managing Containers

### Stop a Container
```bash
podman stop jupyter_lab
```

### Remove a Container
```bash
podman rm jupyter_lab
```

### Remove an Image
```bash
podman rmi quay.io/jupyter/base-notebook
```

---

## 6. Persisting Data with Volumes

### Create Local Directory
```bash
mkdir -p ~/jupyter-data
```

### Run Container with Volume Mount
```bash
podman run -d \
  --name jupyter_lab \
  -p 8888:8888 \
  -v ~/jupyter-data:/home/jovyan/work \
  quay.io/jupyter/base-notebook
```

### Purpose

- Prevent data loss when containers are removed  
- Persist notebooks on the host system  

---

## 7. Project 2: Containerizing Ollama for Local LLMs

### Pull Ollama Image
```bash
podman pull docker.io/alpine/ollama
```

### Run Ollama Container
```bash
podman run -d \
  --name ollama \
  -p 11434:11434 \
  docker.io/alpine/ollama
```

### Pull an LLM Model
```bash
podman exec -it ollama ollama pull gemma3:270m
```

### Verify Ollama
```bash
podman logs ollama
```

---

## 8. Interacting with the LLM via API

### Send a Chat Request
```bash
curl http://localhost:11434/api/chat -d '{
  "model": "gemma3:270m",
  "messages": [
    { "role": "system", "content": "You are a helpful assistant" },
    { "role": "user", "content": "Explain containerization" }
  ],
  "stream": false
}'
```

---

## 9. Podman Networking for Multi-Container Applications

### Create a Network
```bash
podman network create llm-net
```

### Run Ollama on the Network
```bash
podman run -d \
  --name ollama \
  --network llm-net \
  -p 11434:11434 \
  docker.io/alpine/ollama
```

### Concept

- Containers communicate using container names  
- No need for IP addresses  
- `ollama` becomes a hostname  

---

## 10. Project 3: Creating a Flask Web App with an LLM Backend

### Objective

- Build a Flask frontend  
- Send user prompts to a local LLM  
- Display responses in a browser  

---

## 11. Flask Application Code

### LLM Request Function
```python
import requests

def gemma3(user_prompt, style):
    url = "http://ollama:11434/api/chat"
    payload = {
        "model": "gemma3:270m",
        "messages": [
            {
                "role": "system",
                "content": f"You are a helpful assistant. Respond in a formal and {style} style."
            },
            {
                "role": "user",
                "content": user_prompt
            }
        ],
        "stream": False
    }

    response = requests.post(url, json=payload)
    return response.json()['message']['content']
```

### Flask Web Server
```python
from flask import Flask, request

app = Flask(__name__)

@app.route('/')
def index():
    return """
    <form action='/' method='POST'>
        Text: <textarea name='user_prompt'></textarea><br>
        Style: <input name='style' type='text'><br>
        <button type='submit'>Ask</button>
    </form>
    """

@app.route('/', methods=['POST'])
def ask():
    user_prompt = request.form.get('user_prompt')
    style = request.form.get('style')
    result = gemma3(user_prompt, style)
    return f"<textarea>{result}</textarea>"

app.run(host='0.0.0.0', port=5000)
```

---


## 12. Access and Verify

### Open Browser
```
http://localhost:5000
```

### Check Containers
```bash
podman ps
```

### View Logs
```bash
podman logs flask-app
podman logs ollama
```

---

## 13. Troubleshooting Notes (WSL)

- Podman may work even if `podman machine` fails  
- Ensure correct port mappings  
- Ensure containers share the same network  
- Flask must bind to `0.0.0.0`  

---

## 14. Summary

- Podman provides daemonless containerization  
- Containers simplify dependency management  
- Volumes ensure data persistence  
- Networks enable microservice architectures  
- Local LLMs can power full-stack applications  
- Flask + Ollama mirrors real-world AI systems  


Week 2 Session 1 Completed..!!!

