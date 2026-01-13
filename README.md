# AWS EKS NGINX Deployment with CI/CD

This project demonstrates an end-to-end deployment of a containerized NGINX application on AWS EKS with auto-scaling, ALB Ingress, and CI/CD automation.

---

## 🚀 Project Overview
- Deployed NGINX application on AWS EKS
- Implemented CI/CD pipeline to build and deploy Docker images
- Enabled Horizontal Pod Autoscaler (HPA)
- Exposed application using AWS Application Load Balancer (ALB)

---

## 🛠️ Tech Stack
- AWS EKS
- Docker
- Kubernetes
- Jenkins / GitHub Actions
- Amazon ECR
- AWS Load Balancer Controller

---

## 📁 Repository Structure

README.md  
Dockerfile  
index.html  
k8s/  
&nbsp;&nbsp;namespace.yaml  
&nbsp;&nbsp;deployment.yaml  
&nbsp;&nbsp;service.yaml  
&nbsp;&nbsp;hpa.yaml  
&nbsp;&nbsp;ingress.yaml  

---

## ⚙️ Deployment Steps

### 1. Create Namespace
kubectl apply -f k8s/namespace.yaml

### 2. Deploy Application
kubectl apply -f k8s/deployment.yaml

### 3. Expose Service
kubectl apply -f k8s/service.yaml

### 4. Enable Auto Scaling
kubectl apply -f k8s/hpa.yaml

### 5. Expose Application via ALB
kubectl apply -f k8s/ingress.yaml

---

## ✅ Validation
kubectl get pods -n test-app  
kubectl get hpa -n test-app  
kubectl get ingress -n test-app  

Access the application:  
http://<ALB-DNS-NAME>

---

## 📌 Outcome
- Scalable and highly available application
- Zero-downtime deployments
- Automated CI/CD pipeline

---

## 👤 Author
**Saurabh Singh**  
AWS Cloud & DevOps Engineer
