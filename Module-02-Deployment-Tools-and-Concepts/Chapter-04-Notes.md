# 📘 Chapter 4 – FastAPI Development, Testing & Deployment
## Week 2 – Session 4
## Creating APIs, Data Validation, File Handling, Dockerization & Hosting

In this session, we focused on building a real backend service using FastAPI. We learned how to design API routes, process GET and POST requests, validate inputs using Pydantic models, manage file uploads, test endpoints using terminal tools, protect sensitive data with environment variables, package the application with Docker, and deploy the server online for evaluation.

---

# 🔹 1. Project Workflow Overview

The development process follows a structured pipeline from coding to deployment.

Workflow:

1. Develop FastAPI backend locally
2. Test all endpoints
3. Deploy server to the cloud
4. Host frontend on GitHub Pages
5. External server sends request to your API
6. API replies immediately
7. Frontend sends follow-up request for grading

Important points:

- API must respond quickly
- Responses should be proper JSON
- Deployment must be publicly accessible
- Flow should be fully automated

---

# 🔹 2. Introduction to FastAPI

FastAPI is a modern framework used to create APIs with Python efficiently.

Why FastAPI?

- High speed performance
- Simple and clean syntax
- Built-in validation
- Automatic documentation
- Supports asynchronous operations

Install required tools:

```bash
pip install fastapi uvicorn python-multipart
```

Packages explanation:

- fastapi → builds APIs
- uvicorn → runs the server
- python-multipart → enables file uploads

---

# 🔹 3. Starting the Server

Launch the application with:

```bash
uvicorn main:app --reload
```

Explanation:

- main → python file name
- app → FastAPI instance
- --reload → restarts server automatically after changes

Open in browser:

```
http://127.0.0.1:8000
```

---

# 🔹 4. Creating Simple GET Endpoints

GET requests are used to retrieve information.

Example:

```python
from fastapi import FastAPI

app = FastAPI()

@app.get("/")
def index():
    return {"status": "API is running"}
```

Common uses:

- server health checks
- fetching records
- basic responses

---

# 🔹 5. Working with Path Parameters

Path parameters allow dynamic URLs.

Example:

```python
@app.get("/products/{product_id}")
def get_product(product_id: int):
    return {"product": product_id}
```

URL example:

```
/products/7
```

Used when:

- requesting specific data
- accessing unique resources

---

# 🔹 6. Using Query Parameters

Query parameters provide optional filtering.

Example:

```python
@app.get("/filter")
def filter_data(keyword: str = ""):
    return {"search": keyword}
```

URL example:

```
/filter?keyword=python
```

Useful for:

- search
- filtering
- sorting

---

# 🔹 7. Data Validation with Pydantic

Pydantic ensures incoming data follows a defined structure.

Example:

```python
from pydantic import BaseModel

class Person(BaseModel):
    name: str
    age: int
```

Advantages:

- automatic type validation
- prevents invalid input
- consistent response format
- fewer runtime errors

---

# 🔹 8. Handling POST Requests

POST requests send data to the server.

Example:

```python
@app.post("/people")
def add_person(person: Person):
    return person
```

Typically used for:

- creating new entries
- submitting forms
- sending structured data

---

# 🔹 9. Uploading Files

FastAPI supports handling files through multipart forms.

Single file:

```python
from fastapi import UploadFile, File

@app.post("/upload")
async def upload_file(file: UploadFile = File(...)):
    return {"name": file.filename}
```

Multiple files:

```python
@app.post("/uploads")
async def upload_files(files: list[UploadFile]):
    return {"total": len(files)}
```

Common use cases:

- images
- documents
- datasets

---

# 🔹 10. Testing APIs Using curl

curl allows quick testing from the terminal.

GET request:

```bash
curl http://127.0.0.1:8000/
```

POST request:

```bash
curl -X POST http://127.0.0.1:8000/people \
-H "Content-Type: application/json" \
-d '{"name":"Lakshmi","age":22}'
```

Benefits:

- fast testing
- no browser required
- easy debugging

---

# 🔹 11. Automating Tests with Scripts

Manual testing is repetitive. Scripts make it faster.

Example script:

```bash
#!/bin/bash

curl http://127.0.0.1:8000/
curl http://127.0.0.1:8000/products/3
```

Run with:

```bash
bash test.sh
```

This improves development speed.

---

# 🔹 12. Managing Secrets Securely

Sensitive information should not be hardcoded.

Install:

```bash
pip install python-dotenv
```

Create `.env`:

```
SECRET_KEY=abcdef
```

Access in Python:

```python
import os
from dotenv import load_dotenv

load_dotenv()
secret = os.getenv("SECRET_KEY")
```

Advantages:

- secure storage
- safer deployment
- better practice

---

# 🔹 13. Containerizing with Docker

Docker packages the application and its dependencies together.

Sample Dockerfile:

```dockerfile
FROM python:3.10

WORKDIR /app

COPY requirements.txt .
RUN pip install -r requirements.txt

COPY . .

CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "7860"]
```

Why Docker?

- consistent environment
- easy sharing
- smooth deployment

---

# 🔹 14. Deploying the Application

Deploy the container so it can be accessed publicly.

Steps:

1. Choose hosting platform
2. Upload project files
3. Include Dockerfile
4. Start deployment
5. Obtain public URL

Example:

```
https://your-api.hf.space
```

Submit this link for evaluation.

---

# 🔹 Objectives of This Session

After completing this session, you should be able to:

- create FastAPI applications
- design endpoints
- handle GET and POST methods
- validate input data
- upload files
- test APIs using curl
- automate checks
- manage environment variables
- use Docker
- deploy services online

---

## 🎉 Session 4 Completed 🎉
