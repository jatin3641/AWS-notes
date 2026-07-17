# 🚀 Deploying a Python Machine Learning Project on AWS EC2 using WinSCP

> A complete step-by-step guide for deploying a Python Machine Learning application on an **Amazon EC2 Ubuntu Server**, transferring project files using **WinSCP**, setting up a Python virtual environment, installing dependencies, and running the application.

---

![AWS](https://img.shields.io/badge/AWS-EC2-orange?style=for-the-badge&logo=amazonaws)
![Ubuntu](https://img.shields.io/badge/Ubuntu-20.04-E95420?style=for-the-badge&logo=ubuntu&logoColor=white)
![Python](https://img.shields.io/badge/Python-3.x-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-Web_Framework-000000?style=for-the-badge&logo=flask)
![Scikit--Learn](https://img.shields.io/badge/Scikit--Learn-ML-F7931E?style=for-the-badge&logo=scikitlearn)
![WinSCP](https://img.shields.io/badge/WinSCP-File_Transfer-blue?style=for-the-badge)

---

# 📖 Overview

This project demonstrates how to deploy a **Python Machine Learning application** on an **Amazon EC2 Ubuntu instance** using **WinSCP** for file transfer. The guide walks through creating an EC2 instance, configuring security settings, setting up Python, creating a virtual environment, installing project dependencies, uploading project files, and launching the application.

This deployment workflow is commonly used for hosting Flask applications, machine learning models, and Python-based web services in the cloud.

---

# 🎯 Objectives

- Launch an Amazon EC2 Instance
- Configure Security Groups
- Connect to EC2
- Install Python 3 and pip
- Create a Virtual Environment
- Transfer Project Files using WinSCP
- Install Flask and Scikit-Learn
- Run the Python Application
- Deploy Machine Learning Projects on AWS

---

# 📋 Prerequisites

Before starting, make sure you have:

- AWS Account
- Ubuntu EC2 Instance
- SSH Key Pair (.pem)
- WinSCP Installed
- Python Machine Learning Project
- Internet Connection

---

# 🏗 Project Architecture

```text
                Local Computer
                      │
                      │
                 WinSCP (SFTP)
                      │
                      ▼
          Amazon EC2 Ubuntu Server
                      │
          ┌───────────┴───────────┐
          │                       │
          ▼                       ▼
    Python Virtual Env      Project Files
          │                       │
          └───────────┬───────────┘
                      ▼
                Flask Application
                      │
                      ▼
               Machine Learning Model
```

---

# 🚀 Step 1 — Launch an Amazon EC2 Instance

Login to the **AWS Management Console**

```
AWS Console
      │
      ▼
EC2 Dashboard
      │
      ▼
Launch Instance
```

### Configure the Instance

| Setting | Value |
|----------|-------|
| AMI | Ubuntu Server 20.04 LTS |
| Instance Type | t2.micro |
| Storage | Default |
| Security Group | SSH (22), HTTP (80) |
| Key Pair | Create or Select Existing |

Click

```
Launch Instance
```

---

# 🔐 Step 2 — Configure Security Group

Allow the following inbound rules:

| Type | Port | Source |
|------|------|--------|
| SSH | 22 | Your IP |
| HTTP | 80 | Anywhere |
| HTTPS | 443 | Anywhere *(Optional)* |

---

# 💻 Step 3 — Connect to EC2

Connect using EC2 Instance Connect or SSH

```bash
ssh -i your-key.pem ubuntu@YOUR_PUBLIC_IP
```

---

# 🔄 Step 4 — Update Ubuntu

```bash
sudo apt update
```

---

# 🐍 Step 5 — Install Python

```bash
sudo apt install python3 -y
```

```bash
sudo apt install python3-pip -y
```

Verify

```bash
python3 --version
```

```bash
pip3 --version
```

---

# 📁 Step 6 — Create Project Directory

```bash
mkdir myproject
```

Move into the directory

```bash
cd myproject
```

---

# 🌐 Step 7 — Create Virtual Environment

```bash
python3 -m venv .venv
```

Activate the environment

```bash
source .venv/bin/activate
```

Your terminal should now display

```text
(.venv)
```

---

# 📤 Step 8 — Upload Project using WinSCP

## Download WinSCP

Download from

```
https://winscp.net/
```

---

## Connect to EC2

Configure the following:

| Field | Value |
|--------|-------|
| File Protocol | SFTP |
| Host Name | EC2 Public IP / DNS |
| Port | 22 |
| Username | ubuntu |
| Private Key | your-key.pem |

Click

```
Login
```

---

## Transfer Files

Navigate to

### Local Panel

```
Machine Learning Project
```

Example

```text
ML-Project/
│
├── app.py
├── requirements.txt
├── model.pkl
├── templates/
├── static/
└── dataset.csv
```

Remote Panel

```text
/home/ubuntu/myproject
```

Drag and drop all project files.

---

# 📦 Step 9 — Install Dependencies

Install Flask

```bash
pip install flask
```

Install Scikit-Learn

```bash
pip install scikit-learn
```

Or install everything at once

```bash
pip install -r requirements.txt
```

---

# ▶ Step 10 — Run the Application

```bash
python3 app.py
```

Example Output

```text
Running on http://127.0.0.1:5000/
```

---

# 🌍 Step 11 — Access the Application

If Flask is configured with

```python
app.run(host="0.0.0.0", port=5000)
```

Open your browser

```
http://YOUR_PUBLIC_IP:5000
```

Example

```
http://13.233.120.100:5000
```

---

# 📂 Deployment Workflow

```text
Launch EC2
      │
      ▼
Connect via SSH
      │
      ▼
Update Ubuntu
      │
      ▼
Install Python
      │
      ▼
Create Project Folder
      │
      ▼
Create Virtual Environment
      │
      ▼
Activate Environment
      │
      ▼
Upload Project (WinSCP)
      │
      ▼
Install Dependencies
      │
      ▼
Run Flask Application
      │
      ▼
Access Application in Browser
```

---

# 📜 Complete Command Sequence

```bash
sudo apt update

sudo apt install python3 -y

sudo apt install python3-pip -y

mkdir myproject

cd myproject

python3 -m venv .venv

source .venv/bin/activate

pip install flask

pip install scikit-learn

python3 app.py
```

---

# 📁 Recommended Project Structure

```text
Machine-Learning-Deployment/
│
├── app.py
├── requirements.txt
├── model.pkl
├── dataset.csv
├── templates/
├── static/
├── screenshots/
├── README.md
└── LICENSE
```

---

# 📚 Technologies Used

- Amazon Web Services (AWS)
- Amazon EC2
- Ubuntu Server
- Python 3
- Flask
- Scikit-Learn
- WinSCP
- SSH
- Linux Terminal

---

# 🎓 Learning Outcomes

After completing this project, you will understand:

- Amazon EC2 Deployment
- Ubuntu Server Administration
- Python Environment Setup
- Virtual Environments
- Flask Deployment
- Machine Learning Deployment
- WinSCP File Transfer
- Linux Commands
- AWS Security Groups
- Cloud Application Hosting

---

# 🔒 Security Best Practices

- Restrict SSH access to your IP address.
- Keep Ubuntu packages updated.
- Use virtual environments for dependency isolation.
- Store secrets using environment variables.
- Do not expose `.pem` files publicly.
- Configure HTTPS for production deployments.
- Use IAM roles with least-privilege permissions.

---

# 👨‍💻 Author

**Ishan Ali**

**B.Tech Computer Science Engineering (Cyber Security & Forensics)**

- ☁️ AWS Cloud Computing
- 🔐 Cyber Security
- 🐍 Python Development
- 🤖 Machine Learning
- 🚀 DevOps
- 🐧 Linux Administration

---

# ⭐ Support

If you found this project helpful, consider giving it a **⭐ Star** on GitHub.

---

# 📄 License

This project is licensed under the **MIT License**.

---

> **Disclaimer:** This repository is intended for educational purposes only. Always secure your AWS resources and never expose sensitive credentials or private keys.
