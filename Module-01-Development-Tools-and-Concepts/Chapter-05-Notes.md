# 📘 Chapter 5 – Git & GitHub Workflow
## Week 1 – Session 5

# Git Setup, SSH Keys, Cloning & Repository Management

This session focuses on setting up Git and GitHub securely, managing repositories, and understanding real-world collaboration workflows.

---

## 1. Importance of Git & GitHub

## Git
- **:contentReference[oaicite:0]{index=0}** is a distributed version control system.
- Tracks changes in source code.
- Enables collaboration with teams.
- Maintains project history.
- Allows reverting mistakes safely.

## GitHub
- **:contentReference[oaicite:1]{index=1}** is a cloud platform for hosting Git repositories.
- Enables sharing and collaboration.
- Acts as a remote backup for projects.

---

## 2. Installing Git

- Git is installed inside WSL (Ubuntu).
- Used to manage repositories locally.
- Connects local projects to GitHub.
- Tracks commits and changes.

---

## 3. Creating a Repository on GitHub

Steps:
- Create a new repository on GitHub.
- Choose public or private visibility.
- Optionally add a README file.

This repository acts as the remote origin.

---

## 4. SSH Key Authentication

Problem:
- GitHub no longer supports password-based authentication.

Solution:
- Use SSH keys for secure authentication.

Benefits:
- Password-free login.
- Secure trusted connection.
- Faster workflows.

Process:
- Generate SSH key pair.
- Copy public key.
- Add key to GitHub account.
- Test SSH connection.

---

## 5. Cloning a Repository

Cloning means:
- Downloading a copy of a remote repository to the local machine.

After cloning:
- Work locally.
- Edit files.
- Commit changes.
- Push updates back to GitHub.

---

## 6. Basic Git Workflow

Standard development cycle:
1. Stage changes
2. Commit changes
3. Push to remote repository

Flow:
```bash
git add → git commit → git push
```
---

## 7. Troubleshooting Common Git Errors

Connection errors:
Missing or incorrect SSH key.

Permission errors:
Wrong GitHub account.
No access to repository.

Solutions:
Add correct SSH key.
Verify GitHub permissions.

---

## 8. Why WSL / Linux for Git?

Benefits:
Linux-native Git tooling.
Better compatibility.
Easier Docker integration.
Smoother development workflows.

---

## 9. GitHub Copilot

GitHub Copilot is an AI-powered coding assistant.

Features:
Code generation
Function suggestions
Documentation help
Improves developer productivity.

---

## 10. Pull Requests

Pull requests are used for collaboration.

Workflow:
Create a new branch.
Make changes.
Open a pull request.
Review and merge.

Commonly used in team environments.

---

# Objectives of This Session

By the end of this session:

-Git is installed and configured.
-SSH authentication is working.
-Repositories can be cloned locally.
-Changes can be committed and pushed.
-Collaboration workflows are understood.
