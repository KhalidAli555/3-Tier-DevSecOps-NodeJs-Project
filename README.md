````markdown
# 🚀 3-Tier DevSecOps CI/CD Pipeline on Kubernetes

A production-like **3-Tier DevSecOps Project** demonstrating an end-to-end CI/CD pipeline using **Jenkins**, **Docker**, **SonarQube**, **Trivy**, **MySQL**, and **Kubernetes (kubeadm)**.

The project automates source code integration, code quality analysis, security scanning, Docker image creation, image publishing, and deployment to a Kubernetes cluster.

---

## 📌 Project Overview

This project demonstrates a complete DevSecOps workflow for deploying a three-tier web application.

### Application Components

- **Frontend:** React.js
- **Backend:** Node.js (Express.js)
- **Database:** MySQL

### CI/CD Pipeline

The Jenkins pipeline automatically performs the following tasks:

- Checkout source code from GitHub
- Install application dependencies
- Run SonarQube Static Code Analysis
- Validate SonarQube Quality Gate
- Build Docker images
- Scan Docker images using Trivy
- Push Docker images to Docker Hub
- Deploy the application to Kubernetes using kubeadm
- Verify successful deployment

---

# 🏗 Project Architecture

```text
                               Developer
                                   │
                                   ▼
                           GitHub Repository
                                   │
                                   ▼
                          Jenkins CI/CD Pipeline
                                   │
        ┌──────────────────────────┼──────────────────────────┐
        │                          │                          │
        ▼                          ▼                          ▼
 Source Code Build         SonarQube Analysis          Trivy Scan
                                   │
                                   ▼
                          Docker Image Build
                                   │
                                   ▼
                        Push Images to Docker Hub
                                   │
                                   ▼
                   Kubernetes Cluster (kubeadm)
                                   │
                ┌──────────────────┴──────────────────┐
                ▼                                     ▼
        Frontend Deployment                  Backend Deployment
                │                                     │
                └──────────────┬──────────────────────┘
                               ▼
                         MySQL Database
                               │
                               ▼
                            End Users
```

---

# 🏛 Application Architecture

```text
                    +----------------+
                    |     User       |
                    +--------+-------+
                             |
                             ▼
                  +----------------------+
                  | Kubernetes Service   |
                  +----------+-----------+
                             |
               +-------------+--------------+
               |                            |
               ▼                            ▼
      +----------------+          +------------------+
      | React Frontend | <------> | Node.js Backend  |
      +----------------+          +--------+---------+
                                           |
                                           ▼
                                   +---------------+
                                   | MySQL Database|
                                   +---------------+
```

---

# 🛠 Tech Stack

## Frontend

- React.js

## Backend

- Node.js
- Express.js

## Database

- MySQL

## DevOps

- Git
- GitHub
- Jenkins
- Docker
- Docker Hub
- Kubernetes
- kubeadm
- kubectl

## DevSecOps

- SonarQube
- Trivy

## Operating System

- Ubuntu Linux

---

# 🧰 Tools Used

| Tool | Purpose |
|------|---------|
| Git | Version Control |
| GitHub | Source Code Repository |
| Jenkins | CI/CD Automation |
| Docker | Containerization |
| Docker Hub | Image Registry |
| SonarQube | Static Code Analysis |
| Trivy | Container Vulnerability Scanning |
| Kubernetes | Container Orchestration |
| kubeadm | Kubernetes Cluster Setup |
| kubectl | Kubernetes Management |
| MySQL | Relational Database |

---

# 📋 Prerequisites

Before running this project, ensure the following tools are installed.

- Git
- Node.js (18+)
- Docker
- Docker Hub Account
- Jenkins
- SonarQube
- Trivy
- Kubernetes
- kubeadm
- kubectl

---

# 📁 Project Structure

```text
3-tier-devsecops-project/
│
├── api/
│   ├── package.json
│   ├── Dockerfile
│   └── ...
│
├── client/
│   ├── package.json
│   ├── Dockerfile
│   └── ...
│
├── k8s/
│   ├── namespace.yaml
│   ├── mysql-deployment.yaml
│   ├── mysql-service.yaml
│   ├── backend-deployment.yaml
│   ├── backend-service.yaml
│   ├── frontend-deployment.yaml
│   ├── frontend-service.yaml
│   └── ...
│
├── Jenkinsfile
│
├── screenshots/
│   ├── architecture.png
│   ├── jenkins-dashboard.png
│   ├── jenkins-pipeline.png
│   ├── sonarqube-dashboard.png
│   ├── trivy-scan.png
│   ├── docker-images.png
│   ├── kubernetes-pods.png
│   ├── kubernetes-services.png
│   ├── mysql-running.png
│   └── application.png
│
└── README.md
```

---

# ⚙** Local Setup**

Clone the repository

```bash
git clone <repository-url>

cd 3-tier-devsecops-project
```

Install Backend Dependencies

```bash
cd api

npm install
```

Install Frontend Dependencies

```bash
cd ../client

npm install
```

Start Backend

```bash
cd api

npm start
```

Start Frontend

```bash
cd client

npm start
```

Open your browser

```
http://localhost:3000
```

---

# 🔄 Jenkins CI/CD Pipeline

The Jenkins pipeline automates the entire software delivery lifecycle.

### Pipeline Stages

- Checkout Source Code
- Install Dependencies
- SonarQube Analysis
- SonarQube Quality Gate
- Docker Image Build
- Trivy Image Scan
- Push Docker Images to Docker Hub
- Kubernetes Deployment
- Deployment Verification

---

# 🚀 CI/CD Workflow

```text
GitHub
   │
   ▼
Jenkins
   │
   ├── Checkout Source Code
   ├── Install Dependencies
   ├── SonarQube Analysis
   ├── Quality Gate
   ├── Docker Build
   ├── Trivy Scan
   ├── Docker Push
   ├── Kubernetes Deployment
   └── Deployment Verification
```

---

# 🐳 Docker

Build Backend Image

```bash
cd api

docker build -t khalidale/backend:latest .
```

Build Frontend Image

```bash
cd client

docker build -t khalidale/frontend:latest .
```

Push Images

```bash
docker push khalidale/backend:latest

docker push khalidale/frontend:latest
```

---

# 📊 SonarQube Analysis

Start SonarQube

```bash
docker run -d \
--name sonarqube \
-p 9000:9000 \
sonarqube:lts-community
```

Run Sonar Scanner

```bash
sonar-scanner
```

SonarQube performs:

- Static Code Analysis
- Code Smells Detection
- Bug Detection
- Vulnerability Detection
- Security Hotspots
- Quality Gate Validation

---

# 🔒 Trivy Security Scan

Backend Image

```bash
trivy image khalidale/backend:latest
```

Frontend Image

```bash
trivy image khalidale/frontend:latest
```

Trivy detects:

- Critical Vulnerabilities
- High Vulnerabilities
- Medium Vulnerabilities
- Low Vulnerabilities
- Misconfigurations
- Secrets

---

# ☸ Kubernetes Deployment

Create Namespace

```bash
kubectl apply -f k8s/namespace.yaml
```

Deploy MySQL

```bash
kubectl apply -f k8s/mysql-deployment.yaml

kubectl apply -f k8s/mysql-service.yaml
```

Deploy Backend

```bash
kubectl apply -f k8s/backend-deployment.yaml

kubectl apply -f k8s/backend-service.yaml
```

Deploy Frontend

```bash
kubectl apply -f k8s/frontend-deployment.yaml

kubectl apply -f k8s/frontend-service.yaml
```

Verify Deployment

```bash
kubectl get all -n devsecops

kubectl get pods -n devsecops

kubectl get svc -n devsecops

kubectl get deployments -n devsecops

kubectl get nodes
```

---

# ✨ Project Features

- Three-Tier Architecture
- React Frontend
- Node.js Backend
- MySQL Database
- Dockerized Application
- Jenkins CI/CD Pipeline
- SonarQube Static Code Analysis
- Trivy Image Vulnerability Scanning
- Docker Hub Integration
- Kubernetes Deployment using kubeadm
- Automated Build and Deployment
- DevSecOps Best Practices

---

# 🎯 Learning Outcomes

Through this project, I gained practical experience in:

- Git & GitHub
- Jenkins CI/CD Pipelines
- Docker Containerization
- Docker Hub
- SonarQube Integration
- Trivy Security Scanning
- Kubernetes Deployments
- Kubernetes Services
- MySQL Deployment on Kubernetes
- kubeadm Cluster Management
- kubectl Administration
- DevSecOps Best Practices

---

# 🚀 Future Enhancements

- Helm Charts
- Argo CD (GitOps)
- Prometheus Monitoring
- Grafana Dashboards
- NGINX Ingress Controller
- Horizontal Pod Autoscaler (HPA)
- SSL/TLS with Cert-Manager
- Multi-Environment Deployment (Development, Staging, Production)
- Automated Rollback Strategy

---

Contributions, suggestions, and feedback are always welcome.
````
