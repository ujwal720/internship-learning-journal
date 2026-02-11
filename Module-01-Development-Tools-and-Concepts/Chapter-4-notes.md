# 📘 Chapter 4 – Development Tools & Project Setup
## Week 1 – Session 4

# VS Code, Homebrew, Pyenv, UV, GitHub CLI & LLM Tools

This session focuses on setting up a complete development environment required for building intelligent applications.

---

## 1. Development Environment Setup

- macOS is Unix-based and closely aligned with Linux.
- Most Linux commands work directly on macOS.
- Windows users should use WSL for Linux compatibility.

Goal:
Create a Linux-like development environment for consistent workflows.

---

## 2. Installing VS Code

**:contentReference[oaicite:0]{index=0}** is a lightweight and powerful code editor.

Steps:
- Download VS Code
- Move it to the Applications folder
- Launch and grant permissions
- Connect GitHub account
- Enable GitHub Education Pack
- Activate Copilot for AI assistance

Benefits:
- Code editor + terminal
- Rich extension ecosystem
- Built-in Git support
- AI-assisted coding

---

## 3. Homebrew Package Manager

**:contentReference[oaicite:1]{index=1}** is a package manager for macOS.

Equivalent tools:
- macOS → brew
- Linux → apt
- Windows → winget

Used to install:
- Python
- Git
- CLI tools
- Development utilities

Purpose:
- Simplifies software installation
- Handles dependencies automatically

---

## 4. Python Version Management using Pyenv

**:contentReference[oaicite:2]{index=2}** solves Python version conflicts.

Problem:
Different projects require different Python versions.

Solution:
- Install multiple Python versions
- Switch globally or per project
- Avoid dependency conflicts

Core concepts:
- Global Python version
- Local (project-level) Python version

---

## 5. UV – Python Project Manager

**:contentReference[oaicite:3]{index=3}** is a modern, fast Python package and project manager.

Advantages over pip:
- Faster dependency resolution
- Lightweight
- Automatic virtual environments
- Clean project structure

Features:
- Initialize projects
- Add/remove dependencies
- Dependency locking
- Auto Git initialization

---

## 6. GitHub CLI (gh)

**:contentReference[oaicite:4]{index=4}** enables GitHub operations directly from the terminal.

Functions:
- Repository creation
- Authentication
- Pushing code
- Managing commits and issues

Basic workflow:
- git add
- git commit
- gh repo create
- git push

Benefit:
No browser required.

---

## 7. LLM Command-Line Tool

LLM CLI enables interaction with AI models from the terminal.

Supports:
- **:contentReference[oaicite:5]{index=5}**
- **:contentReference[oaicite:6]{index=6}**

Features:
- Ask questions
- Generate code
- Summarize content
- Transcribe audio
- Automate tasks

Requires:
- API keys

---

## 8. Gemini Configuration

Steps:
- Install LLM CLI
- Install Gemini plugin
- Set API key
- Run Gemini models from terminal

Use cases:
- Text generation
- Translation
- Audio transcription

---

## Objectives of This Session

By the end of this session:
- Development environment is ready
- Python versions are managed cleanly
- Projects are structured properly
- GitHub is accessible from terminal
- AI models can be used via CLI
