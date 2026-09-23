🚀 CI/CD Pipeline for Web Application Deployment on AWS EKS

📌 Project Overview

This project demonstrates an end-to-end CI/CD pipeline using GitHub Actions** to build, analyze, containerize, and deploy a web application to **Amazon EKS (Elastic Kubernetes Service)**.

The infrastructure is provisioned using Terraform, while GitHub Actions automates the application build, security checks, code-quality analysis, Docker image creation, and deployment workflow.

The main goal of this project was to gain practical experience in implementing a **DevOps CI/CD workflow using GitHub Actions, Docker, Kubernetes, AWS EKS, Terraform, SonarQube, and Trivy**.

---

🏗️ Architecture

"
                    Developer
                       │
                       │ git push
                       ▼
                 GitHub Repository
                       │
                       ▼
              ┌──────────────────┐
              │  GitHub Actions  │
              │      CI/CD       │
              └────────┬─────────┘
                       │
          ┌────────────┼─────────────┐
          │            │             │
          ▼            ▼             ▼
      Compile       Trivy        SonarQube
      /Build       Security      Code Quality
          │            │             │
          └────────────┼─────────────┘
                       │
                       ▼
                 Docker Build
                       │
                       ▼
                 Docker Hub
                       │
                       ▼
                  AWS EKS
                       │
              ┌────────┴────────┐
              │                 │
         Worker Node 1     Worker Node 2
              │                 │
              └────────┬────────┘
                       │
                       ▼
                 Application Pods
                       │
                       ▼
                    Internet

🛠️ Technologies Used
CI/CD | GitHub Actions | GitHub Self-Hosted Runner | Cloud | AWS | Amazon EKS | EC2 | VPC | IAM | Security Groups | Internet Gateway
Infrastructure as Code | Terraform | Containers | Docker | Docker Hub | Kubernetes | Kubernetes | kubectl | Deployment | Service
Security & Code Quality | Trivy | SonarQube | Application | Web Application

🔄 CI/CD Workflow

The GitHub Actions pipeline performs the following stages:

Git Push
   │
   ▼
Checkout Source Code
   │
   ▼
Compile Application
   │
   ▼
Dependency Resolution
   │
   ▼
Trivy Security Scan
   │
   ▼
SonarQube Code Analysis
   │
   ▼
Build Docker Image
   │
   ▼
Login to Docker Hub
   │
   ▼
Push Docker Image
   │
   ▼
Deploy to AWS EKS
   │
   ▼
Application Available

-------------

🔁 Failure Handling Approach

Instead of immediately destroying and recreating the entire infrastructure, I followed a structured troubleshooting approach:

Pipeline Failure
      │
      ▼
Read Error Message
      │
      ▼
Identify Failed Stage
      │
      ▼
Check Logs
      │
      ▼
Verify AWS / Docker / Kubernetes Configuration
      │
      ▼
Fix Root Cause
      │
      ▼
Run Terraform Plan / Pipeline Again
      │
      ▼
Verify Deployment

🎯 Project Outcome

The final workflow automates the process from:

Developer Code
      ↓
GitHub
      ↓
GitHub Actions
      ↓
Build
      ↓
Security Scan
      ↓
SonarQube Analysis
      ↓
Docker Build
      ↓
Docker Hub
      ↓
AWS EKS
      ↓
Kubernetes Pods
      ↓
Web Application
      ↓
Internet
