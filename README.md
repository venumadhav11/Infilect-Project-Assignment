# Infilect-Project-Assignment

Tech Stack and Choices
| Component     | Technology         | Reasoning                                   |
|---------------|--------------------|---------------------------------------------|
| Backend       | FastAPI (Python)   | Lightweight, async, ideal for REST APIs     |
| Frontend      | React + Chart.js   | Efficient UI rendering and real-time charts |
| Containerization | Docker          | Standardized, portable deployments          |
| Local Orchestration | Docker Compose, Kubernetes (minikube/k3s) | Realistic dev/test environment |
| CI/CD         | GitHub Actions     | Free-tier automation and integration        |
| Registry      | Docker Hub         | Free public image hosting                   |
********************************************************************************************************
Backend: Python with FastAPI – Lightweight and perfect for exposing REST APIs quickly.
Frontend: React with Chart.js – Robust for building dynamic UI and real-time chart updates.
Docker & Docker Compose – Simplified local testing and containerization.
GitHub Actions – Free-tier CI/CD automation pipeline.
Kubernetes – Local deployment using minikube or kind
********************************************************************************************************

Local Deployment Guide

Prerequisites

- Docker & Docker Compose
- Node.js & npm
- Python 3.10+
- kubectl + minikube/k3s

Steps

```bash
git clone <your-repo-url>
cd monitoring-dashboard

# Start with Docker Compose
docker-compose up --build

# Access:
# Frontend: http://localhost:3001
# Backend: http://localhost:8000/metrics
***********************************************
1. Clone the repository
2. Navigate to project root
3. Run `docker-compose up --build`
4. Access frontend athttp://localhost:3001
5. Backend is available at http://localhost:8000/metrics
*************************************************

CI/CD Pipeline (GitHub Actions)
Trigger: PRs and merges to main

Steps:
Lint and test code
Build and push Docker images
Apply Kubernetes manifests
Secrets required:
DOCKER_USERNAME
DOCKER_PASSWORD
YAML: .github/workflows/main.yml
***********************************************************
CI/CD Pipeline Overview
GitHub Actions workflow is triggered on pull requests and merges to `main`.
• Runs unit tests and linters
• Builds Docker images and pushes to Docker Hub
• Applies Kubernetes manifests using `kubectl`
• Uses GitHub secrets to manage sensitive data
***********************************************************


Accessing Services
Service	URL
Frontend	http://localhost:3001
Backend	http://localhost:8000/metrics

*********************************************************


Logs can be viewed via Docker logs or by attaching to container using `docker logs.

# Docker logs
docker logs <container_name>

# Restart
docker-compose restart

# Kubernetes logs
kubectl logs deployment/<name>
*********************************************************
