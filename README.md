# Jerney - Production-Style DevSecOps GitOps Platform

![AWS](https://img.shields.io/badge/AWS-EKS-orange)
![Terraform](https://img.shields.io/badge/IaC-Terraform-purple)
![Kubernetes](https://img.shields.io/badge/Kubernetes-EKS-blue)
![GitHub Actions](https://img.shields.io/badge/CI/CD-GitHub_Actions-black)
![ArgoCD](https://img.shields.io/badge/GitOps-ArgoCD-red)
![Docker](https://img.shields.io/badge/Container-Docker-blue)
![Trivy](https://img.shields.io/badge/Security-Trivy-green)
![Checkov](https://img.shields.io/badge/Security-Checkov-darkgreen)

Production-style full-stack blog platform deployed on AWS EKS using Docker, Kubernetes, Terraform, GitHub Actions CI, DevSecOps scanning, and GitOps Continuous Deployment with ArgoCD.

---

# Project Overview

Jerney is a modern 3-tier blog application built to demonstrate a complete production-style DevOps lifecycle from infrastructure provisioning to automated Kubernetes deployments.

This project includes:

* Frontend application using React
* Backend REST API using Node.js + Express
* PostgreSQL database
* Docker containerization
* Kubernetes orchestration
* AWS EKS deployment
* Terraform Infrastructure as Code
* GitHub Actions CI pipeline
* GitOps Continuous Deployment using ArgoCD
* DevSecOps security scanning using Trivy, Checkov, and Hadolint
* GHCR container image management
* Kubernetes networking and storage

---

# ⚙️ Tech Stack

| Category               | Tools Used                       |
| ---------------------- | -------------------------------- |
| Cloud                  | AWS                              |
| Containerization       | Docker                           |
| Orchestration          | Kubernetes (EKS)                 |
| Infrastructure as Code | Terraform                        |
| CI Pipeline            | GitHub Actions                   |
| CD / GitOps            | ArgoCD                           |
| Image Registry         | GitHub Container Registry (GHCR) |
| Security Scanning      | Trivy, Checkov, Hadolint         |
| Frontend               | React                            |
| Backend                | Node.js, Express                 |
| Database               | PostgreSQL                       |
| Version Control        | Git & GitHub                     |

---

# CI/CD + GitOps Workflow

Developer Push
      │
      ▼
GitHub Actions CI Pipeline
      │
      ├── Lint Code
      ├── Dependency Audit
      ├── Docker Build
      ├── Trivy Image Scan
      ├── Checkov IaC Scan
      ├── Hadolint Dockerfile Scan
      ├── Push Images to GHCR
      └── Update Kubernetes Manifest
                    │
                    ▼
              Git Repository Updated
                    │
                    ▼
         ArgoCD Detects Manifest Change
                    │
                    ▼
          Automatic Deployment to EKS
                    │
                    ▼
            Kubernetes Rolling Update


# DevSecOps Security Implementation

This project integrates security scanning directly into the CI pipeline.

## Security Tools Used

### Trivy

Used for:

* Docker image vulnerability scanning
* OS package scanning
* Dependency vulnerability scanning

### Checkov

Used for:

* Terraform security scanning
* Kubernetes manifest security scanning
* Infrastructure misconfiguration detection

### Hadolint

Used for:

* Dockerfile linting
* Docker best practices validation

---

# Kubernetes Components

The application is deployed on AWS EKS using Kubernetes manifests.

## Kubernetes Resources Used

* Deployments
* Services
* Persistent Volume Claims
* ConfigMaps
* Secrets
* Network Policies
* Readiness Probes
* Liveness Probes

---

# Terraform Infrastructure

Infrastructure provisioning is fully automated using Terraform.

## AWS Resources Provisioned

* VPC
* Public & Private Subnets
* Internet Gateway
* Route Tables
* Security Groups
* EKS Cluster
* EKS Worker Nodes
* IAM Roles & Policies

---

# Container Registry

Docker images are stored in GitHub Container Registry (GHCR).

## Images

```text
Backend:
ghcr.io/<github-username>/jerney-devops-project/jerney-backend

Frontend:
ghcr.io/<github-username>/jerney-devops-project/jerney-frontend
```

---

# Project Structure


jerney-devops-project/
│
├── .github/workflows/      # GitHub Actions CI pipeline
├── backend/                # Node.js backend application
├── frontend/               # React frontend application
├── terraform/              # Terraform infrastructure code
├── k8s/                    # Kubernetes manifests
├── assets/                 # Architecture diagrams
├── screenshots/            # Project screenshots
├── docker-compose.yml
├── README.md
└── .gitignore
```

# Deployment Validation

The application deployment was validated successfully on AWS EKS.

Since this project was built in a cost-optimized lab environment, application access was verified using Kubernetes port-forwarding.

kubectl port-forward svc/jerney-frontend 8172:80 -n jerney

Application accessed locally via:

http://127.0.0.1:8172

# Useful Kubernetes Commands

## Check Pods


kubectl get pods -A


## Check Services


kubectl get svc -A


## Check Nodes


kubectl get nodes


## Check Deployments


kubectl get deployments -A

---

# Key Features

* Automated CI pipeline using GitHub Actions
* GitOps Continuous Deployment using ArgoCD
* Infrastructure provisioning using Terraform
* AWS EKS deployment automation
* Docker image lifecycle management
* DevSecOps vulnerability scanning
* Kubernetes networking and storage
* Automated image updates in manifests
* Rolling deployments on Kubernetes
* Production-style DevOps workflow

---

# Future Enhancements

* AWS Load Balancer Controller
* Kubernetes Ingress
* HTTPS using ACM
* Helm Charts
* Prometheus & Grafana Monitoring
* Loki Logging Stack
* HPA Autoscaling
* External Secrets Manager
* Canary Deployments
* Blue/Green Deployment Strategy

---

# What This Project Demonstrates

This project demonstrates real-world DevOps engineering concepts including:

* Infrastructure as Code (IaC)
* CI/CD automation
* GitOps deployment strategy
* Kubernetes orchestration
* DevSecOps implementation
* Container lifecycle management
* AWS cloud deployment
* Production-style deployment workflows
* Automated security validation
* Kubernetes deployment troubleshooting

---

# Author

## Sneha Basuthkar

DevOps Engineer | AWS | Kubernetes | Terraform | GitHub Actions | GitOps | ArgoCD

GitHub:

https://github.com/snehabasuthkar108

If You Like This Project

Give this repository a ⭐ on GitHub.
