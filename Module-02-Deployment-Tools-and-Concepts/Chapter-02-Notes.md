### WEEK 2 - Session 2 Notes : Containers, FastAPI & Modern Deployment Platforms
This document provides an end-to-end overview of modern web development and deployment concepts, including containers, static hosting, APIs, serverless platforms, and deployment constraints.

---

## 1. Containers vs Virtual Machines

### Virtual Machines (VMs)
- Run a full operating system
- Each VM has its own kernel
- Heavy resource usage
- Slower startup times

### Containers
- Share the host machine’s kernel
- Package only application code and dependencies
- Lightweight and fast
- Start quickly

### Practical Usage
In production systems, applications are often split into:
- Frontend container
- Backend/API container
- Database container

Each component can be deployed and scaled independently.

---

## 2. Podman vs Docker

### Docker
- Uses a background daemon
- Typically requires root privileges
- Widely used and supported

### Podman
- Daemon-less architecture
- Supports rootless containers
- More secure by default
- Docker-compatible CLI

Conceptually, both tools work the same way.

---

## 3. GitHub Pages

GitHub Pages is a static site hosting service.

### Key Characteristics
- Hosts static files only (HTML, CSS, JS)
- Deploys from a selected branch
- Looks for `index.html` by default
- Markdown files are not rendered unless processed (e.g., Jekyll)

### Common Use Cases
- Documentation
- Portfolios
- Static project websites

---

## 4. Deploying a Site with GitHub Pages

### Steps
1. Create a GitHub repository
2. Add an `index.html` file
3. Open repository settings
4. Enable GitHub Pages
5. Select branch and save

### Common Issues
- Wrong branch selected
- Missing `index.html`
- Navigation or sidebar configuration problems

---

## 5. FastAPI

FastAPI is a Python framework for building APIs.

### Features
- High performance
- Native async support
- Automatic request validation
- Automatic API documentation

### Notes
- Designed for backend APIs
- Does not render frontend UI
- Database integration is optional

---

## 6. HTTP Methods

• GET
  - Retrieves data from the server
  - Does not modify server state
  - Parameters are usually sent in the URL (query params)
  - Safe and idempotent

• POST
  - Sends data in the request body
  - Usually JSON
  - Used to create or process data
  - Not idempotent

• PUT
  - Replaces an existing resource entirely
  - Sends full updated data in the request body
  - Idempotent (same request → same result)

• PATCH
  - Partially updates an existing resource
  - Sends only the fields to be updated
  - More efficient than PUT for small changes

• DELETE
  - Removes a resource from the server
  - Idempotent
  - Usually does not include a request body

• HEAD
  - Same as GET but returns headers only
  - Used to check resource existence or metadata

• OPTIONS
  - Returns supported HTTP methods for a resource
  - Commonly used in CORS preflight requests
```bash
• Example (POST Request Body):
  {
    "name": "example",
    "value": 10
  }
```

## 7. Vercel Deployment Model
• Vercel is a serverless deployment platform

• Characteristics
  - Uses Function-as-a-Service (FaaS)
  - No persistent running server
  - Functions are short-lived
  - Designed for fast API responses

• GitHub Integration
  - Connects directly to GitHub repositories
  - Automatically deploys on every push
  - Supports branch preview deployments

## 8. FastAPI Automatic Documentation
• FastAPI automatically generates interactive API documentation

• Available Endpoints
```bash
  - /docs → Swagger UI
  - /redoc → ReDoc UI
```

• Benefits
  - Test endpoints directly in the browser
  - Send GET and POST requests
  - Useful for debugging and understanding APIs

## 9. Vercel Limitations
• Free / Hobby Plan Limits
  - Maximum execution time: 300 seconds (5 minutes)
  - Limited CPU resources
  - Read-only file system
  - Cannot spawn subprocesses
  - WebSockets are unreliable
  - Logs retained for 1 hour

• Implications
  - Long-running jobs will fail
  - Background workers are unsupported
  - Not suitable for real-time or streaming applications

## 10. Deploying with Vercel CLI
• Install Vercel CLI
```bash
  - npm install -g vercel
```
• Login to Vercel
```bash
  - vercel login
```
• Deploy Project
```bash
  - vercel
```

• Deploy to Production
```bash
  - vercel --prod
```

• Common Configuration Files
```bash
  - vercel.json
  - requirements.txt
```

• Incorrect configuration will result in deployment errors

## 11. Local Development with ngrok
    
• ngrok exposes a local server to the public internet

• Start Tunnel
```
  - ngrok http 8000
```

• Use Cases
  - Webhook testing
  - External API callbacks
  - Sharing local development servers

## 12. Environment Variables
• Environment variables store sensitive information securely

• Why Use Environment Variables
  - Prevent hardcoding secrets
  - Avoid committing keys to GitHub
  - Easier configuration across environments

• Example (Linux / macOS)
  - export OPENAI_API_KEY="your_api_key_here"

• Access in Python
  - import os
  - os.getenv("OPENAI_API_KEY")

## 13. Managing Environment Variables on Vercel
• Add Environment Variable
  - vercel env add OPENAI_API_KEY

• Pull Environment Variables Locally
  - vercel env pull .env

## 14. CORS (Cross-Origin Resource Sharing)
• CORS is a browser security mechanism

• Purpose
  - Controls which origins can access a backend
  - Prevents unauthorized cross-origin requests

• Context
  - When frontend and backend run on different domains or ports, CORS rules must be configured to allow communication
  - FastAPI provides middleware for configuring CORS

Summary

• Containers are lightweight alternatives to virtual machines

• Podman and Docker are container engines

• GitHub Pages hosts static content only

• FastAPI is ideal for modern API development

• Vercel is optimized for short-lived serverless functions

• Serverless platforms impose strict execution limits

• Environment variables are essential for security

• CORS must be handled for frontend-backend communication
