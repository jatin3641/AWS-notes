# ☁️ Deploying a Website on AWS EC2 Using Apache & GitHub

> A complete hands-on guide for launching an Amazon EC2 instance, installing Apache Web Server, deploying a website from GitHub, and hosting it publicly on AWS.

---

![AWS](https://img.shields.io/badge/AWS-EC2-orange?style=for-the-badge&logo=amazonaws)
![Amazon Linux](https://img.shields.io/badge/Amazon-Linux-232F3E?style=for-the-badge&logo=amazonlinux)
![Apache](https://img.shields.io/badge/Apache-Web_Server-D22128?style=for-the-badge&logo=apache)
![Git](https://img.shields.io/badge/Git-Version_Control-F05032?style=for-the-badge&logo=git)
![GitHub](https://img.shields.io/badge/GitHub-Repository-181717?style=for-the-badge&logo=github)
![Linux](https://img.shields.io/badge/Linux-Terminal-FCC624?style=for-the-badge&logo=linux&logoColor=black)

---

# 📖 Overview

This project demonstrates how to deploy a static website on an **Amazon EC2** instance using **Apache HTTP Server** and **GitHub**. The guide covers launching an EC2 virtual machine, configuring networking and security, installing a web server, cloning a GitHub repository, and making the website accessible over the internet.

This project is ideal for beginners learning **AWS Cloud Computing**, **Linux Administration**, **Web Hosting**, and **DevOps fundamentals**.

---

# 🎯 Objectives

- Launch an Amazon EC2 Instance
- Configure Security Groups
- Connect to EC2 using SSH
- Install Apache HTTP Server
- Install Git
- Clone a GitHub Repository
- Deploy a Static Website
- Host the Website on AWS
- Understand Cloud Deployment Workflow

---

# 📋 Prerequisites

Before starting, ensure you have:

- AWS Account
- Amazon EC2 Access
- AWS Key Pair (.pem)
- GitHub Repository
- Internet Connection
- Basic Linux Knowledge

---

# 🏗 Project Architecture

```text
                 Internet
                     │
                     ▼
          AWS Management Console
                     │
                     ▼
              Amazon EC2 Instance
                     │
         ┌───────────┴───────────┐
         │                       │
         ▼                       ▼
 Apache HTTP Server        GitHub Repository
         │                       │
         └───────────┬───────────┘
                     ▼
              Static Website
                     │
                     ▼
              Public Browser
```

---

# 🚀 Step 1 — Sign in to AWS

Open the AWS Management Console

```text
https://aws.amazon.com/console/
```

Log in using your AWS account credentials.

---

# 🖥 Step 2 — Open EC2 Dashboard

Navigate to

```text
AWS Console
      │
      ▼
Services
      │
      ▼
EC2
```

---

# ☁️ Step 3 — Launch an EC2 Instance

Click

```
Launch Instance
```

### Configure Instance

| Setting | Value |
|----------|-------|
| Name | My-Web-Server |
| AMI | Amazon Linux 2 |
| Instance Type | t2.micro *(Free Tier)* |
| Key Pair | Create or Select Existing |
| Storage | Default (8 GB) |
| Security Group | Allow SSH & HTTP |

---

## Configure Security Group

Allow the following inbound rules:

| Type | Protocol | Port | Source |
|------|----------|------|--------|
| SSH | TCP | 22 | Your IP / Anywhere |
| HTTP | TCP | 80 | Anywhere |
| HTTPS | TCP | 443 | Anywhere |

Click

```
Launch Instance
```

---

# 🔑 Step 4 — Connect to EC2

Wait until the instance status is **Running**.

Select the instance

```
Connect
      │
      ▼
EC2 Instance Connect
```

Or connect via SSH

```bash
ssh -i your-key.pem ec2-user@YOUR_PUBLIC_IP
```

---

# 🔄 Step 5 — Update the System

```bash
sudo yum update -y
```

---

# 🌐 Step 6 — Install Apache Web Server

Install Apache

```bash
sudo yum install -y httpd
```

Start Apache

```bash
sudo systemctl start httpd
```

Enable Apache on Boot

```bash
sudo systemctl enable httpd
```

Check Status

```bash
sudo systemctl status httpd
```

---

# 📦 Step 7 — Install Git

```bash
sudo yum install -y git
```

Verify Installation

```bash
git --version
```

---

# 📥 Step 8 — Deploy Website from GitHub

Navigate to the web directory

```bash
cd /var/www/html
```

Remove the default page

```bash
sudo rm -rf *
```

Clone the repository

```bash
sudo git clone https://github.com/thebugbounter/preet-watches.git .
```

---

# 🔒 Step 9 — Configure Permissions

```bash
sudo chown -R apache:apache /var/www/html
```

```bash
sudo chmod -R 755 /var/www/html
```

---

# 🔄 Step 10 — Restart Apache

```bash
sudo systemctl restart httpd
```

---

# 🌍 Step 11 — Access the Website

Open your browser

```
http://YOUR_PUBLIC_IP
```

or

```
http://YOUR_PUBLIC_DNS
```

Example

```
http://ec2-3-110-25-120.ap-south-1.compute.amazonaws.com
```

Your website should now be live.

---

# 📂 Project Workflow

```text
AWS Login
     │
     ▼
Launch EC2
     │
     ▼
Configure Security Group
     │
     ▼
Connect to EC2
     │
     ▼
Update Packages
     │
     ▼
Install Apache
     │
     ▼
Install Git
     │
     ▼
Clone GitHub Repository
     │
     ▼
Configure Permissions
     │
     ▼
Restart Apache
     │
     ▼
Website Live
```

---

# 📁 Project Structure

```
AWS-EC2-Website-Deployment/
│
├── README.md
├── screenshots/
├── deployment-guide/
├── apache-config/
├── website-files/
└── LICENSE
```

---

# 💻 Commands Used

## Update System

```bash
sudo yum update -y
```

## Install Apache

```bash
sudo yum install -y httpd
```

## Start Apache

```bash
sudo systemctl start httpd
```

## Enable Apache

```bash
sudo systemctl enable httpd
```

## Install Git

```bash
sudo yum install -y git
```

## Clone Repository

```bash
sudo git clone https://github.com/thebugbounter/preet-watches.git .
```

## Set Permissions

```bash
sudo chown -R apache:apache /var/www/html
```

```bash
sudo chmod -R 755 /var/www/html
```

## Restart Apache

```bash
sudo systemctl restart httpd
```

---

# 📚 Technologies Used

- Amazon Web Services (AWS)
- Amazon EC2
- Amazon Linux
- Apache HTTP Server
- Git
- GitHub
- Linux Terminal
- SSH

---

# 🎓 Learning Outcomes

After completing this project, you will understand:

- AWS EC2
- Linux Administration
- Apache Web Server
- Git & GitHub
- Cloud Deployment
- Security Groups
- SSH Access
- Static Website Hosting
- Web Server Management
- DevOps Basics

---

# 🔒 Security Best Practices

- Restrict SSH access to your own IP address.
- Keep the operating system updated.
- Regularly update Apache packages.
- Use HTTPS with SSL certificates for production.
- Configure IAM roles with the principle of least privilege.
- Enable CloudWatch monitoring and logging.
- Back up your EC2 instance and website regularly.

---

# 👨‍💻 Author

**Ishan Ali**

**B.Tech Computer Science Engineering (Cyber Security & Forensics)**

- ☁️ Cloud Computing
- 🔐 Cyber Security
- 🚀 DevOps
- 🐧 Linux Administration
- 💻 Full Stack Development

---

# ⭐ Support

If this project helped you, don't forget to **⭐ Star** the repository and share it with others learning AWS.

---

# 📄 License

This project is licensed under the **MIT License**.

---

> **Disclaimer:** This repository is intended for educational purposes only. Always follow AWS security best practices and secure your cloud infrastructure before deploying production applications.
