# 🐍 Jenkins Python Automation Guide

> A complete step-by-step guide to configuring **Jenkins** to execute Python scripts from the Jenkins workspace. This guide covers job creation, source code management, workspace configuration, build execution, and best practices for running Python applications in a Continuous Integration (CI) environment.

---

<p align="center">
  <img src="https://img.shields.io/badge/Jenkins-CI%2FCD-D24939?style=for-the-badge&logo=jenkins&logoColor=white">
  <img src="https://img.shields.io/badge/Python-3.x-3776AB?style=for-the-badge&logo=python&logoColor=white">
  <img src="https://img.shields.io/badge/Git-Version_Control-F05032?style=for-the-badge&logo=git">
  <img src="https://img.shields.io/badge/GitHub-Repository-181717?style=for-the-badge&logo=github">
  <img src="https://img.shields.io/badge/Platform-Windows%20%7C%20Linux-blue?style=for-the-badge">
</p>

---

# 📖 Overview

This project demonstrates how to configure **Jenkins** to execute Python scripts directly from the **Jenkins Workspace**. Jenkins automatically checks out source code from a version control system (such as GitHub), stores it inside its workspace, and executes the Python application during the build process.

This workflow is commonly used in **Continuous Integration (CI)** pipelines for Python applications, automation scripts, machine learning projects, and DevOps workflows.

---

# 📚 Table of Contents

- Overview
- Features
- Prerequisites
- Project Workflow
- Create a Jenkins Job
- Configure Source Code Management
- Configure Build Steps
- Execute Python Script
- Build the Project
- Workspace Management
- Best Practices
- Technologies Used
- Learning Outcomes

---

# ✨ Features

- Jenkins Freestyle Project
- GitHub Integration
- Workspace Execution
- Python Script Automation
- Windows & Linux Support
- Continuous Integration Workflow
- Build Monitoring
- Console Output Logs

---

# 📋 Prerequisites

Before you begin, ensure you have:

- Jenkins Installed
- Python 3 Installed
- Git Installed *(Optional)*
- GitHub Repository *(Optional)*
- Administrator Access to Jenkins

---

# 🏗 Project Architecture

```text
             GitHub Repository
                     │
                     ▼
               Jenkins Job
                     │
                     ▼
          Jenkins Workspace
                     │
                     ▼
              Python Script
                     │
                     ▼
             Build Execution
                     │
                     ▼
            Console Output
```

---

# 🚀 Step 1 — Create a Jenkins Job

Open Jenkins Dashboard

```
http://localhost:8080
```

Navigate to

```text
Dashboard
      │
      ▼
New Item
```

Enter a project name

```
Python-Script-Job
```

Select

```
Freestyle Project
```

Click

```
OK
```

---

# 📂 Step 2 — Configure Source Code Management

If your Python project is stored on GitHub:

Navigate to

```text
Source Code Management
      │
      ▼
Git
```

Enter your repository URL

```text
https://github.com/username/repository.git
```

If the repository is private

- Add GitHub Credentials
- Username
- Personal Access Token (PAT)

Choose the desired branch

```
main
```

or

```
master
```

Save the configuration.

---

# ⚙ Step 3 — Configure Build Step

Navigate to

```text
Build
      │
      ▼
Add Build Step
```

Choose

### Windows

```
Execute Windows Batch Command
```

### Linux / Ubuntu

```
Execute Shell
```

---

# 💻 Windows Build Command

```batch
cd %WORKSPACE%

python script.py
```

or

```batch
cd %WORKSPACE%

python folder\script.py
```

---

# 🐧 Linux Build Command

```bash
cd $WORKSPACE

python3 script.py
```

or

```bash
cd $WORKSPACE

python3 folder/script.py
```

---

# 📂 Jenkins Workspace

Jenkins automatically creates a workspace for every project.

Example

```text
C:\ProgramData\Jenkins\.jenkins\workspace\Python-Script-Job
```

Linux

```text
/var/lib/jenkins/workspace/Python-Script-Job
```

The workspace contains all source files downloaded from the repository.

---

# ▶ Step 4 — Build the Project

Click

```
Build Now
```

Jenkins will

- Clone the Repository
- Open the Workspace
- Execute the Python Script
- Display Build Status

---

# 📊 View Build Logs

Navigate to

```text
Build History
      │
      ▼
Build Number
      │
      ▼
Console Output
```

Example

```text
Started by user Admin

Cloning repository...

Executing Python Script...

Hello Jenkins!

Finished: SUCCESS
```

---

# 📂 Project Workflow

```text
GitHub Repository
        │
        ▼
Jenkins Job
        │
        ▼
Clone Repository
        │
        ▼
Workspace Created
        │
        ▼
Execute Python Script
        │
        ▼
Console Output
        │
        ▼
Build Success
```

---

# 📁 Recommended Project Structure

```text
Python-Script-Job/
│
├── script.py
├── requirements.txt
├── README.md
├── src/
├── data/
└── LICENSE
```

---

# 🐍 Example Python Script

```python
print("Hello from Jenkins Workspace!")
```

---

# 📜 Complete Build Commands

## Windows

```batch
cd %WORKSPACE%

python script.py
```

---

## Linux

```bash
cd $WORKSPACE

python3 script.py
```

---

# 🛠 Best Practices

- Use Python Virtual Environments.
- Install dependencies from `requirements.txt`.
- Keep repositories clean.
- Store secrets using Jenkins Credentials.
- Enable workspace cleanup after builds.
- Use pipelines for complex workflows.
- Monitor build logs regularly.

---

# 📚 Technologies Used

- Jenkins
- Python
- Git
- GitHub
- Windows
- Linux
- Continuous Integration (CI)

---

# 🎯 Learning Outcomes

After completing this guide, you will understand:

- Jenkins Job Creation
- Jenkins Workspace
- GitHub Integration
- Python Automation
- Build Execution
- Console Output Analysis
- Continuous Integration
- Python Script Deployment

---

# 👨‍💻 Author

**Ishan Ali**

**B.Tech Computer Science Engineering (Cyber Security & Forensics)**

- 🔐 Cyber Security
- ☁️ Cloud Computing
- 🐍 Python Development
- 🚀 DevOps
- 🐧 Linux Administration
- 💻 Web Development

---

# ⭐ Support

If this guide helped you, consider giving the repository a **⭐ Star** and sharing it with others learning Jenkins and Python automation.

---

# 📄 License

This project is licensed under the **MIT License**.

---

> **Disclaimer:** This repository is intended for educational purposes only. Always secure your Jenkins server, manage credentials safely, and follow CI/CD best practices when deploying production applications.
