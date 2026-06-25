# Multi-Page Portfolio Site with Automated CI/CD Pipeline

A production-ready DevOps portfolio project demonstrating automated containerization, infrastructure best practices, and standard enterprise Git workflows. 

The project hosts a static multi-page website using an optimized Nginx container, managed entirely through a conditional GitHub Actions pipeline.

## 🚀 Architecture & Workflow Overview

This project implements a strict branch-protection simulation lifecycle:
1. **Feature/Dev Branch (`dev-1`)**: Code changes are made and pushed. The CI pipeline triggers a **Hadolint** syntax and security scan on the `Dockerfile`. Continuous Delivery (DockerHub Push) is automatically **skipped** to protect production.
2. **Main Branch (`main`)**: Once linting passes, code is merged into `main`. The pipeline runs the security lint again, builds the final Docker image, and automatically deploys it to DockerHub with unique commit tags (`github.sha`).

## 🛠️ Tech Stack & Skills Demonstrated

* **Containerization:** Docker, Dockerfile configuration optimization
* **CI/CD Automation:** GitHub Actions (Conditional job matrix, Secrets Management, Hadolint Integration)
* **Web Server:** Nginx (Alpine-based minimal footprint)
* **Version Control:** Git Git Branching Strategy, Git Multi-Folder Workflows, Personal Access Tokens (PAT)
* **Environment:** Linux (WSL2 Ubuntu terminal)

## 📋 Repository Structure

```text
├── .github/
│   └── workflows/
│       └── deploy.yml      # Conditional GitHub Actions Pipeline
├── webpages/
│   ├── index.html          # Core Homepage layout
│   ├── about.html          # Portfolio details
│   └── contact.html        # Professional contact links
├── Dockerfile              # Optimized Nginx Multi-stage/Alpine build configuration
└── .gitignore              # Secure credential and OS tracking bypass filter
```

## 🛠️ How to Run Locally

To pull and run the verified container directly from DockerHub onto your local environment:

```bash
# Pull the latest image
docker pull pyaephyomaung47/portfolio-site:latest

# Run the container locally on port 8080
docker run -d -p 8080:80 --name local-portfolio YOUR_DOCKERHUB_USERNAME/portfolio-site:latest
```
*Open your browser and navigate to `http://localhost:8080` to verify the deployment.*

