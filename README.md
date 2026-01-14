# AWS EKS NGINX Deployment with HPA and CI/CD

## Project Overview
This project demonstrates deploying an NGINX application on AWS EKS using Kubernetes best practices, including autoscaling, ingress configuration, containerization, and CI/CD automation.

---

## Architecture & Components
- AWS EKS Cluster (Managed Node Group)
- Kubernetes Namespace: `test-app`
- NGINX Deployment (2 replicas)
- ClusterIP / NodePort Service
- Horizontal Pod Autoscaler (HPA)
- AWS Load Balancer Controller (ALB Ingress)
- Docker image hosted in Amazon ECR
- CI/CD using GitHub Actions (Jenkins pipeline included)

---

## Kubernetes Resources
- **Namespace:** test-app  
- **Deployment:** nginx-deployment  
- **Service:** nginx-service  
- **HPA:** nginx-hpa  
- **Ingress:** nginx-ingress (ALB)

---

## CI/CD Workflow
On every push to the `main` branch:
1. Docker image is built
2. Image is pushed to Amazon ECR
3. Kubernetes manifests are applied to the EKS cluster

CI/CD is implemented using **GitHub Actions**.  
A **Jenkins pipeline** is also included for demonstration.

---

## Proof of Deployment (Execution Evidence)

This section provides execution proof of the AWS EKS NGINX deployment.

---

### 1. Kubernetes Pods Running
**Command**
```bash
kubectl get pods -n test-app
```bash
kubectl get pods -n test-app
