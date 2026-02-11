
# 🛠️ Hands-On Practice
## Week 1 – Session 1 (Hands-on)

### WSL Installation on Windows

1. Opened Control Panel.
2. Navigated to:
   Programs → Turn Windows features on or off.
3. Enabled:
   - Virtual Machine Platform
   - Windows Hypervisor Platform
   - Windows Subsystem for Linux
4. Clicked OK and restarted the system.

### Installing WSL
- Followed a YouTube tutorial to install WSL.
- Completed the installation successfully.

### Verification
Ran the following command in PowerShell:
```bash
wsl --version
```
## Week 1 – Session 2 (Hands-on)

### Understanding the Need for WSL
- Reviewed why Linux is preferred for development and Data Science.
- Compared WSL with VirtualBox based on performance and resource usage.

### Git & GitHub Exploration
- Learned the purpose of Git for version control.
- Understood how GitHub is used to host and share repositories.
- Studied the basic Git workflow:
  - git add
  - git commit
  - git push

### Linux Terminal Practice
- Opened Ubuntu terminal using WSL.
- Practiced basic navigation commands:
```bash
ls
cd
```
Created directories and files:
```bash
mkdir test_folder
touch test_file.txt
```

Explored Linux directory structure:
```bash
ls /
```
Observed common directories like /home, /etc, /bin, and /usr.

Learned how sudo is used for administrative tasks.

Session 2 hands-on activities completed successfully.

## Week 1 – Session 3 (Hands-on)

### OS Boot Process
- Studied the step-by-step operating system boot process.
- Understood differences between Linux and Windows boot flows.

### Cloud & Virtualization
- Learned how cloud data centers use hypervisors.
- Understood how multiple virtual machines run on one physical server.
- Learned the purpose of RBAC in cloud environments.

### WSL File System Navigation
- Created files using:
```bash
touch NEWFILE
```
Edited files using:
```bash
vi NEWFILE
notepad.exe NEWFILE
```
Viewed file contents using:
```bash
cat NEWFILE
```
Directory Navigation
Practiced navigation using:
```bash
pwd
ls
cd
clear
```
Explored Linux directories:
```bash
ls /
```
Windows File Access
Navigated Windows files from WSL:
```bash
cd /mnt/c/Users
```
VS Code Integration
```bash

Opened project using:

code .
Used Linux terminal directly inside VS Code.
```
Installing Tools
Installed UV:
```bash
pip install uv
```
Installed and tested LLM CLI:
```bash
uv tool install llm
llm "Explain Linux commands"
```
Session 3 hands-on completed successfully.

## Week 1 – Session 4 (Hands-on)

### Environment Setup
- Understood differences between macOS, Linux, and Windows.
- Chose WSL/Linux-style workflow for development consistency.

### VS Code
- Installed Visual Studio Code.
- Connected GitHub account.
- Enabled GitHub Education Pack.
- Activated Copilot for AI-assisted coding.
- Used integrated terminal.

### Homebrew
- Installed Homebrew.
- Added brew to PATH.
- Verified installation.
- Used brew to manage development tools.

### Pyenv
- Installed pyenv.
- Installed multiple Python versions.
- Set global and local Python versions.
- Verified Python switching.

### UV
- Installed UV package manager.
- Initialized a new Python project.
- Added and removed dependencies.
- Observed automatic virtual environment creation.
- Noted auto Git initialization.

### GitHub CLI
- Installed GitHub CLI.
- Authenticated with GitHub.
- Created repositories from terminal.
- Pushed local code using gh and git commands.

### LLM Tool
- Installed LLM CLI using UV.
- Configured API keys.
- Tested AI prompts from terminal.
- Ran commands using Gemini and OpenAI models.

Session 4 hands-on completed successfully.



---

## Week 1 – Session 5 (Hands-on)

### Git Setup
- Installed Git inside WSL (Ubuntu).
- Verified Git installation.

### GitHub Repository
- Created a new repository on GitHub.
- Chose repository visibility.
- Copied repository SSH URL.

### SSH Key Setup
- Generated SSH key pair.
- Added public SSH key to GitHub account.
- Tested SSH connection successfully.

### Cloning Repository
- Cloned the GitHub repository into WSL.
- Navigated into the project directory.

### Making Changes
- Created and edited files locally.
- Staged changes using:
```bash
git add .
```
Committed changes:
```bash
git commit -m "Initial commit"
```

Pushed changes to GitHub:
```bash
git push
```
Troubleshooting

Resolved SSH authentication issues.

Fixed permission-related errors.

Session 5 hands-on completed successfully.

