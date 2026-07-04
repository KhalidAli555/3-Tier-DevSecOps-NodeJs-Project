# 🚀 3-Tier DevSecOps CI/CD Pipeline on Kubernetes

A production-like **3-Tier DevSecOps Project** demonstrating an end-to-end CI/CD pipeline using **Jenkins**, **Docker**, **SonarQube**, **Trivy**, **MySQL**, and **Kubernetes (kubeadm)**.

The project automates source code integration, code quality analysis, security scanning, Docker image creation, image publishing, and deployment to a Kubernetes cluster.

---

## 📌 Project Overview

### Application Components

- **Frontend:** React.js
- **Backend:** Node.js (Express.js)
- **Database:** MySQL

### CI/CD Pipeline

- Checkout source code from GitHub
- Install dependencies
- SonarQube Static Code Analysis
- SonarQube Quality Gate Validation
- Build Docker Images
- Trivy Image Scan
- Push Docker Images to Docker Hub
- Deploy to Kubernetes (kubeadm)
- Verify deployment

---

# 🏛 Application Architecture

```text
User
 │
 ▼
Kubernetes Service
 │
 ├───────────────┐
 ▼               ▼
React       Node.js API
                 │
                 ▼
              MySQL
```

## 🛠 Tech Stack

- React.js
- Node.js / Express.js
- MySQL
- Git & GitHub
- Jenkins
- Docker
- Docker Hub
- SonarQube
- Trivy
- Kubernetes
- kubeadm
- kubectl
- Ubuntu Linux

## 📋 Prerequisites

- Git
- Node.js 18+
- Docker
- Jenkins
- SonarQube
- Trivy
- Kubernetes
- kubeadm
- kubectl

## 📁 Project Structure

```text
3-tier-devsecops-project/
│
├── api/
├── client/
├── k8s/
│   ├── backend/
│   │   ├── deployment.yml
│   │   └── service.yml
│   ├── frontend/
│   │   ├── deployment.yml
│   │   └── service.yml
│   └── mysql/
│       ├── config.yml
│       ├── config1.yml
│       ├── deployment.yml
│       ├── pv.yml
│       ├── pvc.yml
│       ├── secret.yml
│       └── service.yml
├── k8s-prod/
├── Jenkinsfile
├── screenshots/
└── README.md
```

## ⚙ Local Setup

```bash
git clone <repository-url>
cd 3-tier-devsecops-project

cd api
npm install

cd ../client
npm install

cd ../api
npm start

cd ../client
npm start
```

Open: http://localhost:3000

## 🔄 Jenkins Pipeline

1. Checkout Source Code
2. Install Dependencies
3. SonarQube Analysis
4. Quality Gate Validation
5. Docker Build
6. Trivy Image Scan
7. Push Images to Docker Hub
8. Kubernetes Deployment
9. Deployment Verification

## 🐳 Docker

```bash
cd api
docker build -t khalidale/backend:latest .

cd ../client
docker build -t khalidale/frontend:latest .

docker push khalidale/backend:latest
docker push khalidale/frontend:latest
```

## 📊 SonarQube

```bash
docker run -d --name sonarqube -p 9000:9000 sonarqube:lts-community

sonar-scanner
```

## 🔒 Trivy

```bash
trivy image khalidale/backend:latest
trivy image khalidale/frontend:latest
```

## ☸ Kubernetes Deployment

```bash
kubectl apply -f k8s/mysql/secret.yml
kubectl apply -f k8s/mysql/config.yml
kubectl apply -f k8s/mysql/config1.yml
kubectl apply -f k8s/mysql/pv.yml
kubectl apply -f k8s/mysql/pvc.yml
kubectl apply -f k8s/mysql/deployment.yml
kubectl apply -f k8s/mysql/service.yml

kubectl apply -f k8s/backend/deployment.yml
kubectl apply -f k8s/backend/service.yml

kubectl apply -f k8s/frontend/deployment.yml
kubectl apply -f k8s/frontend/service.yml
```

Verify:

```bash
kubectl get pods
kubectl get svc
kubectl get deployments
kubectl get pv
kubectl get pvc
kubectl get configmaps
kubectl get secrets
```

## 📸 Project Screenshots

- architecture.png
- jenkins-dashboard.png
- jenkins-pipeline.png
- sonarqube-dashboard.png
- trivy-scan.png
- docker-images.png
- kubernetes-pods.png
- kubernetes-services.png
- mysql-running.png
- application.png

## ✨ Features

- Three-tier architecture
- React + Node.js + MySQL
- Dockerized application
- Jenkins CI/CD
- SonarQube analysis
- Trivy security scanning
- Docker Hub integration
- Kubernetes deployment with kubeadm
- DevSecOps workflow

## 🎯 Learning Outcomes

- Jenkins Pipelines
- Docker
- Kubernetes
- MySQL on Kubernetes
- SonarQube
- Trivy
- DevSecOps Best Practices

## 🚀 Future Enhancements

- Helm
- Argo CD
- Prometheus
- Grafana
- Ingress Controller
- HPA
- Cert-Manager


If you found this project useful, give it a ⭐ on GitHub.
