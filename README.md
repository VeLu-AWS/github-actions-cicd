# GitHub Actions CI/CD Pipeline
### Auto-Deploy Docker Containerized App to AWS EC2 on Every Git Push

---

## Overview

This repository demonstrates a complete CI/CD pipeline using GitHub Actions
to automatically build a Docker image and deploy it to AWS EC2 whenever
code is pushed to the main branch.

Built as part of DevOps infrastructure work at Patil Rail Infrastructure
Pvt Ltd for Indian Railways technology projects.

---

## Pipeline Flow
---

## Tech Stack

| Tool | Purpose |
|---|---|
| GitHub Actions | CI/CD pipeline automation |
| Docker | Application containerization |
| AWS EC2 | Production server (Ubuntu 22.04) |
| Nginx | Web server inside container |
| SCP | Secure file transfer to EC2 |
| SSH | Remote deployment execution |

---

## Pipeline Steps

| Step | Action |
|---|---|
| 1 | Checkout code from GitHub |
| 2 | Set up Docker Buildx |
| 3 | Build Docker image |
| 4 | Save image as .tar.gz |
| 5 | SCP image to EC2 |
| 6 | SSH → load image → restart container |
| 7 | Verify deployment |
---

## GitHub Secrets Required

Go to repo → Settings → Secrets and variables → Actions → New secret

| Secret | Description |
|---|---|
| `EC2_HOST` | Public IP or Elastic IP of EC2 |
| `EC2_USER` | SSH username (ubuntu) |
| `EC2_SSH_KEY` | Private key (.pem file contents) |

---

## Setup & Usage

```bash
# Clone the repository
git clone https://github.com/VeLu-AWS/github-actions-cicd.git
cd github-actions-cicd

# Add your secrets in GitHub
# Settings → Secrets → EC2_HOST, EC2_USER, EC2_SSH_KEY

# Push to main branch to trigger pipeline
git add .
git commit -m "deploy: trigger CI/CD pipeline"
git push origin main

# GitHub Actions will automatically:
# 1. Build Docker image
# 2. Deploy to EC2
# 3. Verify app is running
```

---

## Project Context

| Detail | Info |
|---|---|
| **Deployed at** | Patil Rail Infrastructure Pvt Ltd |
| **Use case** | Automated deployment for Indian Railways applications |
| **Server** | AWS EC2 — Mumbai (ap-south-1) |
| **Container** & **Reverse Proxy / Web Server**| Docker + Nginx |
| **Deployment Trigger** | Push to main branch |
| **Deployment Type** | CI/CD-based automatic deployment |

---

## Author

**C Sengottuvelu**
AWS Cloud & DevOps Engineer | AWS Certified Solutions Architect – Associate (SAA-C03)
Bengaluru, India
---

## Repository Structure
