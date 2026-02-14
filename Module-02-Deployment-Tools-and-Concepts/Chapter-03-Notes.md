# WEEK 2 Session 3 : Cloud Development & Automation Tools Overview

This chapter documents modern cloud-based development and automation workflows using GitHub Codespaces, Hugging Face Spaces, and GitHub Actions. These tools allow you to develop, deploy, and automate applications with minimal local setup.

---

## 1. Git, WSL, and VS Code Basics

Before introducing cloud tools, the session clarifies how local development tooling fits together.

### Git Usage

Git can be used via CLI or desktop clients.

Core concepts include:

- Cloning repositories  
- Creating and switching branches  
- Committing and pushing changes  

### WSL (Windows Subsystem for Linux)

WSL allows running Linux tools directly on Windows.

- Most development tools (Python, Docker, Git, etc.) are installed inside WSL  
- This enables a Linux-like development experience without a separate virtual machine  

### VS Code

VS Code acts as a code editor and interface.

- It does not install tools itself, but connects to environments such as WSL or Codespaces  
- Think of it as a powerful editor rather than the execution environment  

---

## 2. GitHub Codespaces

GitHub Codespaces provides a fully configured, cloud-hosted development environment.

### Key Features

- Runs VS Code in the browser or locally connected to the cloud  
- No local installation required  
- Identical experience whether accessed via:
  - GitHub UI  
  - VS Code  
  - Command Line Interface (CLI)  

### Configuration with Dev Containers

Codespaces are configured using a `.devcontainer/` directory:

```text
.devcontainer/
├── devcontainer.json
```
The devcontainer.json file defines:

- Programming languages and runtimes

- Required system packages

- VS Code extensions

- Startup commands

This ensures:

- New contributors can start coding immediately

- Consistent environments across teams

- Multiple configurations for different teams or roles

Common Use Cases
- Onboarding new developers quickly

- Teaching or workshops

- Working on projects without powerful local hardware

Limitations
- Automatically stops after 30 minutes of inactivity

- File size limit: 100 MB per file (without Git LFS)

- Recommended repository size: ≤ 1 GB
---
## 3. Deploying Applications with Hugging Face Spaces
Hugging Face Spaces is a platform for hosting machine learning models, datasets, and web applications.

What Are Spaces?
Git-based application deployments

Similar workflow to GitHub repositories

Supports:

- Docker

- FastAPI

- Gradio

- Streamlit

### Git LFS (Large File Storage)

Git LFS
- Required for files larger than 100 MB.

Commonly used for:

- Machine learning models

- Large datasets

### Deployment Workflow
- Create a new Space

- Select Docker as the runtime

- Push application code to the Space repository

- Hugging Face builds and deploys the app automatically

### Runtime Characteristics
Public URL for deployed applications

Typical configuration:

- 2 CPUs

- 16 GB RAM

Spaces shut down automatically after 48 hours of inactivity
---
## 4. Automating Workflows with GitHub Actions
GitHub Actions enables automation directly inside a GitHub repository.

Workflow Configuration
Workflows are defined in:
```
.github/
└── workflows/
    └── workflow-name.yml
```
These YAML files define:

- When the workflow runs (push, pull request, schedule)

- What jobs and steps are executed

- Which environments are used

Example Use Case
A scheduled workflow that:

- Runs daily

- Fetches the International Space Station (ISS) latitude and longitude

- Writes the data to a JSON file

- Commits and pushes the updated file automatically

Common Use Cases
- Continuous Integration (CI)

- Run tests on every push

- Lint and format code

- Continuous Deployment (CD)

- Deploy applications automatically

- Scheduled jobs

- Data collection

- Maintenance scripts
---
## Summary
- This workflow demonstrates a modern development pipeline:

- Codespaces → Develop in the cloud with zero local setup

- Hugging Face Spaces → Deploy applications quickly with Git-based workflows

- GitHub Actions → Automate testing, deployment, and scheduled tasks

- Together, these tools reduce setup friction, improve collaboration, and enable fully automated development lifecycles.
