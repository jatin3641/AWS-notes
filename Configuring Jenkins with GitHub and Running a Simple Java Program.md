# 🚀 Jenkins GitHub Integration & Java Build Automation

> A step-by-step guide to configuring **Jenkins** with **GitHub** and automatically building a simple **Java application** using Continuous Integration (CI). This project demonstrates how to connect Jenkins with a GitHub repository, compile Java source code, and automate builds using GitHub Webhooks.

---

![Jenkins](https://img.shields.io/badge/Jenkins-CI%2FCD-D24939?style=for-the-badge&logo=jenkins&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-Version_Control-181717?style=for-the-badge&logo=github)
![Java](https://img.shields.io/badge/Java-JDK-orange?style=for-the-badge&logo=openjdk)
![Git](https://img.shields.io/badge/Git-Repository-F05032?style=for-the-badge&logo=git)
![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20Linux-blue?style=for-the-badge)

---

# 📖 Overview

This project demonstrates how to integrate **Jenkins** with a **GitHub repository** and automate the build process of a simple Java application. It covers the complete Continuous Integration (CI) workflow, from installing Jenkins plugins to configuring GitHub webhooks that automatically trigger builds whenever code is pushed to the repository.

Using Jenkins and GitHub together enables developers to automate repetitive tasks, detect build issues early, and maintain a reliable software development workflow.

---

# 🎯 Objectives

- Learn Jenkins Continuous Integration (CI)
- Connect Jenkins with GitHub
- Install Git Plugin and GitHub Integration Plugin
- Configure Git repositories in Jenkins
- Build Java applications automatically
- Configure GitHub Webhooks
- Automate project builds
- Monitor build logs
- Understand CI/CD fundamentals

---

# 🛠 Prerequisites

Before starting, ensure the following software is installed:

- Jenkins
- Java JDK (8 or later)
- Git
- GitHub Account
- Internet Connection

Repository Used:

```text
https://github.com/thebugbounter/JenkinsTesting.git
```

---

# 📂 Project Workflow

```text
GitHub Repository
        │
        ▼
Push Source Code
        │
        ▼
GitHub Webhook
        │
        ▼
Jenkins Trigger
        │
        ▼
Clone Repository
        │
        ▼
Compile Java Code
        │
        ▼
Execute Program
        │
        ▼
Build Success
```

---

# 📦 Step 1 — Install Required Jenkins Plugins

1. Open Jenkins

```
http://localhost:8080
```

2. Navigate to

```
Manage Jenkins
        │
        ▼
Manage Plugins
```

3. Install the following plugins:

- Git Plugin
- GitHub Integration Plugin

Click

```
Install without Restart
```

---

# 🏗 Step 2 — Create a New Jenkins Project

1. Open Jenkins Dashboard

2. Click

```
New Item
```

3. Enter

```
GitHub-Java-Test
```

4. Select

```
Freestyle Project
```

5. Click

```
OK
```

---

# 🔗 Step 3 — Configure GitHub Repository

Navigate to

```
Source Code Management
```

Select

```
Git
```

Repository URL

```text
https://github.com/thebugbounter/JenkinsTesting.git
```

If your repository is private:

- Add GitHub Credentials
- Username
- Personal Access Token (PAT)

---

# ⚙ Step 4 — Configure Build Trigger

Navigate to

```
Build Triggers
```

Enable

```
GitHub hook trigger for GITScm polling
```

This allows Jenkins to automatically build whenever code is pushed to GitHub.

---

# 💻 Step 5 — Add Build Commands

## Windows

```batch
javac Hello.java
java Hello
```

---

## Linux / Ubuntu

```bash
javac Hello.java
java Hello
```

---

# ▶ Step 6 — Run the Build

Save the project.

Click

```
Build Now
```

To view output

```
Build History
        │
        ▼
Build Number
        │
        ▼
Console Output
```

---

# 🌐 Step 7 — Configure GitHub Webhook

Go to

```
Repository
    │
    ▼
Settings
    │
    ▼
Webhooks
    │
    ▼
Add Webhook
```

Payload URL

```text
http://<your-jenkins-server>/github-webhook/
```

Example

```text
http://localhost:8080/github-webhook/
```

Content Type

```
application/json
```

Select

```
Just the push event
```

Click

```
Add Webhook
```

---

# 📁 Project Structure

```
JenkinsTesting/
│
├── Hello.java
├── README.md
└── .gitignore
```

---

# 💡 Hello.java Example

```java
public class Hello {

    public static void main(String[] args) {

        System.out.println("Hello from Jenkins CI/CD!");

    }

}
```

---

# 📊 Continuous Integration Flow

```text
Developer
     │
     ▼
Git Commit
     │
     ▼
Git Push
     │
     ▼
GitHub Repository
     │
     ▼
Webhook Trigger
     │
     ▼
Jenkins
     │
     ▼
Clone Repository
     │
     ▼
Compile Java
     │
     ▼
Run Program
     │
     ▼
Build Status
```

---

# 📚 Technologies Used

- Jenkins
- Git
- GitHub
- Java
- GitHub Webhooks
- Windows/Linux
- Continuous Integration (CI)

---

# 🎓 Learning Outcomes

After completing this project you will understand:

- Jenkins Installation
- Jenkins Plugins
- Git Integration
- GitHub Integration
- Java Project Build
- Continuous Integration
- GitHub Webhooks
- Automated Build Process
- Jenkins Console Logs
- CI/CD Workflow

---

# 👨‍💻 Author

**Ishan Ali**

**B.Tech Computer Science Engineering (Cyber Security & Forensics)**

- Cloud Computing
- DevOps
- Cyber Security
- Linux Administration
- Ethical Hacking
- Full Stack Development

---

# ⭐ Support

If you found this project helpful, consider giving it a **⭐ Star** on GitHub.

---

# 📄 License

This project is licensed under the **MIT License**.

---

> **Disclaimer:** This repository is created solely for educational and learning purposes to demonstrate Jenkins Continuous Integration with GitHub and Java.
