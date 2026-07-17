# 🚀 Git & GitHub Complete Guide

> A comprehensive guide to **Git** and **GitHub**, covering installation, repository management, branching, merging, authentication, stashing, tagging, undoing changes, and essential commands for beginners and developers.

---

<p align="center">
  <img src="https://img.shields.io/badge/Git-Version_Control-F05032?style=for-the-badge&logo=git&logoColor=white">
  <img src="https://img.shields.io/badge/GitHub-Code_Hosting-181717?style=for-the-badge&logo=github">
  <img src="https://img.shields.io/badge/Open_Source-Friendly-brightgreen?style=for-the-badge">
  <img src="https://img.shields.io/badge/License-MIT-blue?style=for-the-badge">
</p>

---

# 📖 Overview

Git is a **distributed version control system (DVCS)** that helps developers track changes in source code, collaborate efficiently, and maintain project history. GitHub is a cloud-based platform that hosts Git repositories and enables collaboration through pull requests, issues, and workflows.

This guide provides a practical introduction to Git and GitHub, including installation, repository management, version control, branching strategies, and commonly used commands.

---

# 📚 Table of Contents

- [Features](#-features)
- [Prerequisites](#-prerequisites)
- [Install Git](#-1-install-git)
- [Configure Git](#-2-configure-git)
- [Working with Repositories](#-3-working-with-repositories)
- [Branching & Merging](#-4-branching--merging)
- [Remote Repositories](#-5-pushing--pulling)
- [Undo Changes](#-6-undoing-changes)
- [GitHub Authentication](#-7-github-authentication)
- [Git Stash](#-8-git-stash)
- [Git Tags](#-9-git-tags)
- [.gitignore](#-10-gitignore)
- [Reset & Revert](#-11-reset--revert)
- [Essential Commands](#-essential-commands)

---

# ✨ Features

- Git Installation
- Repository Initialization
- Clone Repositories
- Commit Changes
- Branch Management
- Merge Branches
- GitHub Integration
- Push & Pull Code
- Git Stash
- Git Tags
- Undo Commits
- Personal Access Token Authentication
- Git Ignore
- Reset & Revert

---

# 📋 Prerequisites

- Windows / Linux / macOS
- Internet Connection
- GitHub Account
- Git Installed
- Terminal / Command Prompt

---

# 🏗 Git Workflow

```text
Create Repository
        │
        ▼
Initialize Git
        │
        ▼
Create Files
        │
        ▼
Git Status
        │
        ▼
Git Add
        │
        ▼
Git Commit
        │
        ▼
Git Push
        │
        ▼
GitHub Repository
```

---

# 📥 1. Install Git

Download Git from the official website

```
https://git-scm.com/downloads
```

Verify the installation

```bash
git --version
```

Example Output

```text
git version 2.48.1
```

---

# 👤 2. Configure Git

Configure your Git identity before creating commits.

```bash
git config --global user.name "Your Name"
```

```bash
git config --global user.email "your-email@example.com"
```

Check configuration

```bash
git config --list
```

---

# 📂 3. Working with Repositories

## Initialize a Repository

```bash
git init
```

Creates a hidden `.git` directory to track project history.

---

## Clone a Repository

```bash
git clone https://github.com/username/repository.git
```

Downloads an existing GitHub repository.

---

## Check Repository Status

```bash
git status
```

Displays:

- Modified files
- Untracked files
- Staged files
- Current branch

---

## Add Files

Add a specific file

```bash
git add filename
```

Add all files

```bash
git add .
```

---

## Commit Changes

```bash
git commit -m "Initial Commit"
```

A commit saves the current project state.

---

## View Commit History

Detailed History

```bash
git log
```

Short History

```bash
git log --oneline
```

Graph View

```bash
git log --graph --oneline --all
```

---

# 🌿 4. Branching & Merging

## Create a Branch

```bash
git branch feature-branch
```

---

## Switch Branch

```bash
git switch feature-branch
```

or

```bash
git checkout feature-branch
```

---

## Create & Switch

```bash
git checkout -b feature-branch
```

or

```bash
git switch -c feature-branch
```

---

## Merge Branch

```bash
git checkout main
```

```bash
git merge feature-branch
```

---

## Delete Branch

Local

```bash
git branch -d feature-branch
```

Remote

```bash
git push origin --delete feature-branch
```

---

# ☁️ 5. Pushing & Pulling

## Add Remote Repository

```bash
git remote add origin https://github.com/username/repository.git
```

Verify

```bash
git remote -v
```

---

## Push Code

```bash
git push origin main
```

---

## First Push

```bash
git push -u origin main
```

---

## Pull Changes

```bash
git pull origin main
```

---

## Fetch Changes

```bash
git fetch
```

---

# ↩️ 6. Undoing Changes

## Restore File

```bash
git restore filename
```

Older Method

```bash
git checkout -- filename
```

---

## Unstage File

```bash
git reset filename
```

---

## Undo Last Commit (Keep Changes)

```bash
git reset --soft HEAD~1
```

---

## Undo Last Commit (Discard Changes)

```bash
git reset --hard HEAD~1
```

---

# 🔐 7. GitHub Authentication

GitHub now requires a **Personal Access Token (PAT)** instead of passwords.

Generate a PAT from:

```
GitHub
    │
    ▼
Settings
    │
    ▼
Developer Settings
    │
    ▼
Personal Access Tokens
```

Push using

```bash
git push https://github.com/username/repository.git
```

Use:

- Username
- Personal Access Token

---

# 📦 8. Git Stash

Save temporary changes

```bash
git stash
```

View stash list

```bash
git stash list
```

Restore changes

```bash
git stash pop
```

Delete stash

```bash
git stash drop
```

---

# 🏷 9. Git Tags

Create Tag

```bash
git tag v1.0
```

List Tags

```bash
git tag
```

Push Tags

```bash
git push origin --tags
```

---

# 🚫 10. .gitignore

Example

```gitignore
node_modules/
.env
*.log
*.pyc
__pycache__/
.vscode/
dist/
build/
```

Purpose

- Ignore dependencies
- Ignore environment files
- Ignore logs
- Ignore build files
- Ignore cache files

---

# 🔄 11. Reset & Revert

## Revert Commit

```bash
git revert commit-hash
```

Creates a new commit that undoes previous changes.

---

## Reset Commit

```bash
git reset --hard commit-hash
```

Moves the repository back to a previous commit.

---

# 📂 Complete Git Workflow

```text
Create Project
      │
      ▼
git init
      │
      ▼
Create Files
      │
      ▼
git status
      │
      ▼
git add .
      │
      ▼
git commit
      │
      ▼
git branch
      │
      ▼
git merge
      │
      ▼
git push
      │
      ▼
GitHub Repository
```

---

# 📌 Essential Git Commands

| Command | Description |
|----------|-------------|
| `git init` | Initialize Repository |
| `git clone` | Clone Repository |
| `git status` | Check Status |
| `git add .` | Stage Changes |
| `git commit -m` | Commit Changes |
| `git branch` | Create Branch |
| `git switch` | Switch Branch |
| `git merge` | Merge Branch |
| `git push` | Push to GitHub |
| `git pull` | Pull Latest Changes |
| `git fetch` | Fetch Updates |
| `git log` | View History |
| `git stash` | Save Temporary Changes |
| `git tag` | Create Version Tag |
| `git reset` | Reset Repository |
| `git revert` | Undo Commit |

---

# 🛠 Technologies Used

- Git
- GitHub
- Git CLI
- Markdown
- Version Control

---

# 🎯 Learning Outcomes

After completing this guide, you will understand:

- Git Installation
- Repository Management
- Branching Strategy
- Merge Operations
- GitHub Collaboration
- Remote Repositories
- Git Stash
- Tags & Releases
- Undo Operations
- Version Control Best Practices

---

# 👨‍💻 Author

**Ishan Ali**

**B.Tech Computer Science Engineering (Cyber Security & Forensics)**

- 🔐 Cyber Security
- ☁️ Cloud Computing
- 💻 Web Development
- 🚀 DevOps
- 🐧 Linux Administration
- 🌐 Open Source Enthusiast

---

# ⭐ Support

If this repository helped you, don't forget to **⭐ Star** the repository and share it with others.

---

# 📄 License

This project is licensed under the **MIT License**.

---

> **Disclaimer:** This repository is intended for educational and learning purposes. Git and GitHub are trademarks of their respective owners.
