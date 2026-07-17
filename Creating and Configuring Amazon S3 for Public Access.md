# ☁️ Amazon S3 Public Bucket Configuration Guide

> A complete step-by-step guide to creating an Amazon S3 bucket, configuring public access, managing bucket policies, uploading objects, and implementing security best practices for hosting static files and web content.

---

![AWS](https://img.shields.io/badge/AWS-S3-orange?style=for-the-badge&logo=amazonaws)
![Amazon S3](https://img.shields.io/badge/Amazon-S3-red?style=for-the-badge&logo=amazons3)
![Cloud](https://img.shields.io/badge/Cloud-Storage-blue?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

---

# 📖 Overview

Amazon Simple Storage Service (Amazon S3) is a highly scalable object storage service designed to store and retrieve any amount of data from anywhere. It is commonly used for:

- 🌐 Static Website Hosting
- 📦 File Storage
- 💾 Data Backup
- 📷 Image & Video Hosting
- 📁 Document Sharing
- ☁️ Cloud Storage Solutions

This guide demonstrates how to create an S3 bucket, configure public access, upload files, and apply bucket policies securely.

---

# 🎯 Objectives

- Create an Amazon S3 Bucket
- Configure Bucket Permissions
- Enable Public Access
- Upload Files
- Configure Bucket Policies
- Manage Object Permissions
- Understand AWS Security Best Practices
- Host Static Website Files

---

# 📋 Prerequisites

Before you begin, ensure you have:

- AWS Account
- IAM User with S3 Permissions
- Internet Connection
- AWS CLI *(Optional)*
- Basic Knowledge of AWS Services

---

# 🏗 Architecture

```text
                User
                  │
                  ▼
        AWS Management Console
                  │
                  ▼
            Amazon S3 Bucket
                  │
        ┌─────────┴─────────┐
        │                   │
        ▼                   ▼
 Upload Objects      Bucket Policy
        │                   │
        └─────────┬─────────┘
                  ▼
          Public File Access
```

---

# 🚀 Step 1 — Login to AWS

Open your browser and navigate to

```
https://aws.amazon.com/console/
```

Log in using your AWS credentials.

---

# 📂 Step 2 — Open Amazon S3

From the AWS Console

```
Services
     │
     ▼
Amazon S3
```

---

# 🪣 Step 3 — Create an S3 Bucket

Click

```
Create Bucket
```

Fill in the following details:

| Setting | Value |
|----------|-------|
| Bucket Name | Unique Bucket Name |
| AWS Region | Your Preferred Region |
| Object Ownership | ACLs Disabled (Recommended) |
| Block Public Access | Configure According to Requirement |

Click

```
Create Bucket
```

---

# 🔓 Step 4 — Configure Public Access

Navigate to

```
Bucket
    │
    ▼
Permissions
    │
    ▼
Block Public Access
```

Click

```
Edit
```

Disable public access blocking **only if public access is required**.

> ⚠️ **Warning:** Public buckets should only be used when necessary.

Save the configuration.

---

# 📜 Step 5 — Configure Bucket Policy

Navigate to

```
Bucket
     │
     ▼
Permissions
     │
     ▼
Bucket Policy
```

Paste the following policy.

Replace:

```
YOUR-BUCKET-NAME
```

with your actual bucket name.

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::YOUR-BUCKET-NAME/*"
    }
  ]
}
```

Click

```
Save Changes
```

---

# 📤 Step 6 — Upload Files

Open your bucket.

Click

```
Upload
```

Select your files.

Example:

```
index.html
style.css
script.js
images/
```

Complete the upload process.

---

# 🔑 Step 7 — Configure Object Permissions

While uploading files

```
Permissions
      │
      ▼
Grant Public Read Access
```

Complete the upload.

---

# 🌐 Step 8 — Access Your Files

Your uploaded files will be available at:

```text
https://YOUR-BUCKET-NAME.s3.amazonaws.com/filename
```

Example

```text
https://my-static-website.s3.amazonaws.com/index.html
```

---

# 📁 Project Workflow

```text
AWS Login
     │
     ▼
Open Amazon S3
     │
     ▼
Create Bucket
     │
     ▼
Configure Permissions
     │
     ▼
Disable Public Access Block
     │
     ▼
Add Bucket Policy
     │
     ▼
Upload Files
     │
     ▼
Grant Public Read Access
     │
     ▼
Access Files via URL
```

---

# 🔒 Security Best Practices

- Follow the Principle of Least Privilege.
- Grant public access only when required.
- Enable Versioning.
- Enable Server Access Logging.
- Monitor bucket activity using CloudTrail.
- Encrypt sensitive objects.
- Use IAM Roles instead of Root credentials.
- Review bucket policies regularly.

---

# ⚠️ Troubleshooting

## Access Denied

- Verify Bucket Policy.
- Check IAM Permissions.
- Ensure Block Public Access is disabled if required.
- Confirm object permissions are set correctly.

---

## Bucket Not Accessible

- Verify bucket name.
- Confirm region selection.
- Check Bucket Policy.
- Verify uploaded objects exist.

---

## Objects Return 403 Forbidden

- Ensure files are public.
- Verify policy syntax.
- Confirm object ownership.

---

# 📚 AWS Services Used

- Amazon S3
- AWS IAM
- AWS Management Console
- AWS CLI *(Optional)*
- AWS CloudTrail *(Optional)*

---

# 📖 Learning Outcomes

After completing this project, you will understand:

- Amazon S3 Fundamentals
- Bucket Management
- Object Storage
- Bucket Policies
- IAM Permissions
- Public Access Configuration
- Static Website Hosting
- Cloud Storage Best Practices
- AWS Security

---

# 📂 Repository Structure

```
Amazon-S3-Public-Bucket/
│
├── README.md
├── bucket-policy.json
├── screenshots/
├── sample-files/
├── documentation/
└── LICENSE
```

---

# 👨‍💻 Author

**Ishan Ali**

**B.Tech Computer Science Engineering (Cyber Security & Forensics)**

- Cloud Computing
- AWS
- Cyber Security
- DevOps
- Linux Administration
- Ethical Hacking

---

# ⭐ Support

If you found this repository helpful, consider giving it a **⭐ Star** on GitHub.

---

# 📄 License

This project is licensed under the **MIT License**.

---

> **Disclaimer:** This project is intended for educational and learning purposes. Always follow AWS security best practices when configuring public access to cloud storage resources.
