# 🔐 AWS IAM (Identity and Access Management) Complete Guide

> A comprehensive guide to **AWS Identity and Access Management (IAM)** covering users, groups, roles, policies, permissions, security best practices, and identity management in Amazon Web Services.

---

<p align="center">
  <img src="https://img.shields.io/badge/AWS-IAM-orange?style=for-the-badge&logo=amazonaws">
  <img src="https://img.shields.io/badge/Cloud-Security-blue?style=for-the-badge">
  <img src="https://img.shields.io/badge/Access-Control-green?style=for-the-badge">
  <img src="https://img.shields.io/badge/Identity-Management-red?style=for-the-badge">
  <img src="https://img.shields.io/badge/License-MIT-blue?style=for-the-badge">
</p>

---

# 📖 Overview

**AWS Identity and Access Management (IAM)** is a secure web service that enables you to control access to AWS resources. It allows administrators to create users, groups, and roles while assigning permissions using IAM policies.

IAM helps organizations securely manage authentication, authorization, and resource access without sharing the AWS root account credentials.

This guide demonstrates how to create IAM users, configure IAM roles, manage policies, and implement AWS security best practices.

---

# 📚 Table of Contents

- Overview
- Features
- Prerequisites
- AWS IAM Architecture
- Accessing IAM Dashboard
- Creating IAM Users
- Creating IAM Roles
- Managing IAM Policies
- Attaching Policies
- Security Best Practices
- Technologies Used
- Learning Outcomes
- License

---

# ✨ Features

- Create IAM Users
- Create IAM Groups
- Create IAM Roles
- Manage IAM Policies
- Assign Permissions
- Configure Programmatic Access
- Console Login Access
- Multi-Factor Authentication (MFA)
- Least Privilege Implementation
- IAM Security Best Practices

---

# 📋 Prerequisites

Before you begin, ensure you have:

- AWS Account
- AWS Management Console Access
- Internet Connection
- Basic Knowledge of AWS Services

---

# 🏗 IAM Architecture

```text
                  AWS Account
                        │
                        ▼
               Identity & Access
             Management (IAM)
                        │
        ┌───────────────┼───────────────┐
        │               │               │
        ▼               ▼               ▼
     Users           Groups          Roles
        │               │               │
        └───────────────┼───────────────┘
                        ▼
                  IAM Policies
                        │
                        ▼
                AWS Resources
```

---

# 🚀 Step 1 — Access AWS IAM

Login to the AWS Management Console

```
https://aws.amazon.com/console/
```

Navigate to

```text
AWS Console
      │
      ▼
Services
      │
      ▼
IAM
```

The IAM Dashboard will open.

---

# 👤 Step 2 — Create an IAM User

Navigate to

```text
IAM Dashboard
      │
      ▼
Users
      │
      ▼
Create User
```

### Configure User Details

- Enter Username
- Choose Access Type

Example

```
Username

developer01
```

---

## Select Access Type

Choose one or both options:

✅ AWS Management Console Access

- Allows users to log into the AWS Console.

✅ Programmatic Access

- Allows access using:
  - AWS CLI
  - SDKs
  - APIs

---

## Configure Permissions

You can assign permissions using:

- Attach Policies Directly
- Add User to Existing Group
- Copy Permissions from Another User

Click

```
Next
```

---

## Add Tags (Optional)

Example

| Key | Value |
|-----|-------|
| Department | Development |
| Team | Cloud |
| Environment | Production |

Click

```
Create User
```

---

## Save Credentials

If Programmatic Access is enabled, securely store:

- Access Key ID
- Secret Access Key

> ⚠️ **Important:** The Secret Access Key is displayed only once.

---

# 👥 Step 3 — Create IAM Groups

Groups simplify permission management.

Navigate to

```text
IAM
    │
    ▼
User Groups
    │
    ▼
Create Group
```

Example

```
Developers
```

Attach required policies.

Example

```
AmazonEC2ReadOnlyAccess
```

Add users to the group.

---

# 🔑 Step 4 — Create IAM Roles

Navigate to

```text
IAM
    │
    ▼
Roles
    │
    ▼
Create Role
```

Choose the trusted entity.

Available Options

- AWS Service
- Another AWS Account
- Web Identity
- SAML Federation
- Custom Trust Policy

---

## Attach Permissions

Example Policies

- AmazonS3FullAccess
- AmazonEC2FullAccess
- CloudWatchReadOnlyAccess

---

## Configure Role

Enter

```
Role Name
```

Example

```
EC2-S3-Access
```

Click

```
Create Role
```

---

# 📜 Step 5 — Create IAM Policies

Navigate to

```text
IAM
     │
     ▼
Policies
     │
     ▼
Create Policy
```

You can create policies using:

- Visual Editor
- JSON Editor

---

## Example JSON Policy

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "s3:ListBucket",
        "s3:GetObject"
      ],
      "Resource": "*"
    }
  ]
}
```

Click

```
Review Policy
```

Then

```
Create Policy
```

---

# 🔗 Step 6 — Attach Policies

Navigate to

```text
Users
    │
    ▼
Select User
    │
    ▼
Permissions
    │
    ▼
Add Permissions
```

Choose

```
Attach Policies Directly
```

Search

```
AmazonS3ReadOnlyAccess
```

Click

```
Add Permissions
```

---

# 🔐 Enable Multi-Factor Authentication (MFA)

Navigate to

```text
IAM
    │
    ▼
Users
    │
    ▼
Security Credentials
```

Click

```
Assign MFA Device
```

Supported Devices

- Virtual MFA
- Hardware MFA
- FIDO Security Key

---

# ☁️ Monitor IAM Activity

Use the following AWS services:

- AWS CloudTrail
- Amazon CloudWatch
- AWS IAM Access Analyzer
- AWS Config

These services help monitor authentication events, policy changes, and resource access.

---

# 📂 IAM Workflow

```text
AWS Login
      │
      ▼
Open IAM
      │
      ▼
Create User
      │
      ▼
Create Group
      │
      ▼
Assign Policies
      │
      ▼
Create Role
      │
      ▼
Attach Permissions
      │
      ▼
Enable MFA
      │
      ▼
Monitor Activity
```

---

# 🔒 AWS Security Best Practices

- Follow the Principle of Least Privilege.
- Never use the root account for daily tasks.
- Enable Multi-Factor Authentication (MFA).
- Rotate Access Keys regularly.
- Use IAM Roles instead of long-term credentials.
- Create IAM Groups for permission management.
- Monitor account activity using CloudTrail.
- Review permissions periodically.
- Remove unused users and access keys.
- Use strong password policies.

---

# 📊 Common AWS Managed Policies

| Policy | Description |
|---------|-------------|
| AdministratorAccess | Full AWS Access |
| AmazonS3FullAccess | Full S3 Access |
| AmazonEC2FullAccess | Full EC2 Access |
| IAMReadOnlyAccess | Read-Only IAM Access |
| ReadOnlyAccess | Read-Only AWS Resources |
| PowerUserAccess | Full Access Except IAM |

---

# 📚 Technologies Used

- Amazon Web Services
- AWS IAM
- AWS CloudTrail
- AWS CloudWatch
- AWS CLI
- JSON
- Identity Management

---

# 🎯 Learning Outcomes

After completing this guide, you will understand:

- AWS IAM Fundamentals
- Identity Management
- User Management
- IAM Groups
- IAM Roles
- IAM Policies
- Permission Management
- Programmatic Access
- Multi-Factor Authentication
- Cloud Security Best Practices

---

# 📁 Repository Structure

```text
AWS-IAM-Guide/
│
├── README.md
├── screenshots/
├── iam-policies/
├── sample-json/
├── diagrams/
└── LICENSE
```

---

# 👨‍💻 Author

**Ishan Ali**

**B.Tech Computer Science Engineering (Cyber Security & Forensics)**

- ☁️ AWS Cloud Computing
- 🔐 Cyber Security
- 🛡️ Cloud Security
- 🚀 DevOps
- 🐧 Linux Administration
- 💻 Web Development

---

# ⭐ Support

If this guide helped you, don't forget to **⭐ Star** the repository and share it with others learning AWS.

---

# 📄 License

This project is licensed under the **MIT License**.

---

> **Disclaimer:** This repository is created for educational and learning purposes only. Always follow AWS security best practices and avoid using the root account for routine administrative tasks.
