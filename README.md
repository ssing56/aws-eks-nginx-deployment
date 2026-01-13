# AWS EKS NGINX Deployment with CI/CD

This project demonstrates an end-to-end deployment of a containerized NGINX application on AWS EKS using Kubernetes best practices, CI/CD automation, auto-scaling, and external access via AWS Application Load Balancer (ALB).

---

## 🎯 Objective
Deploy and manage a sample application on AWS EKS with scalability, automation, and production-ready configuration.

---

## 📌 Tasks Covered
1. Created a Kubernetes namespace named test-app  
2. Deployed NGINX with 2 replicas and resource limits  
3. Exposed the application internally using ClusterIP Service on port 80  
4. Configured Horizontal Pod Autoscaler (HPA) with CPU target 60%  
5. Installed AWS Load Balancer Controller using Helm  
6. Exposed application externally using ALB via Kubernetes Ingress  
7. Built Docker image and pushed it to Amazon ECR using CI/CD pipeline  
8. Applied Kubernetes manifests automatically through CI/CD pipeline  

---

## 🛠️ Tech Stack
- AWS EKS
- Docker
- Kubernetes
- Jenkins (CI/CD)
- Amazon ECR
- AWS Load Balancer Controller
- Helm

---

## 📁 Repository Structure

README.md  
Dockerfile  
index.html  
Jenkinsfile  
k8s/  
&nbsp;&nbsp;namespace.yaml  
&nbsp;&nbsp;deployment.yaml  
&nbsp;&nbsp;service.yaml  
&nbsp;&nbsp;hpa.yaml  
&nbsp;&nbsp;ingress.yaml  

---

## ⚙️ Deployment Steps (Manual)

### Step 1: Create Namespace
kubectl apply -f k8s/namespace.yaml  

### Step 2: Deploy Application
kubectl apply -f k8s/deployment.yaml  

### Step 3: Expose Application Internally
kubectl apply -f k8s/service.yaml  

### Step 4: Enable Auto Scaling
kubectl apply -f k8s/hpa.yaml  

### Step 5: Expose Application Externally (ALB)
kubectl apply -f k8s/ingress.yaml  

---

## ☸️ Kubernetes Components Overview

### Namespace
A dedicated namespace test-app is used to isolate application resources.

### Deployment
- NGINX deployed with 2 replicas
- CPU and memory requests & limits configured
- Rolling update strategy ensures zero downtime

### Service
- ClusterIP Service exposes the application internally on port 80

### Horizontal Pod Autoscaler (HPA)
- Automatically scales pods based on CPU utilization
- Target CPU utilization set to 60%

---

## ☁️ AWS Load Balancer Controller

AWS Load Balancer Controller was installed using Helm to enable ALB-based Ingress in EKS.

Responsibilities:
- Automatically creates and manages ALB
- Configures listeners and target groups
- Integrates Kubernetes Ingress with AWS infrastructure

---

## 🌐 Ingress (ALB Exposure)
- Internet-facing ALB is created automatically
- Routes external traffic to ClusterIP Service
- Uses IP mode to directly target pod IPs

---

## 🔁 CI/CD Pipeline (Jenkins)

A Jenkins-based CI/CD pipeline automates the deployment process.

Pipeline Flow:
1. Pulls source code from GitHub  
2. Builds Docker image using Dockerfile  
3. Pushes Docker image to Amazon ECR  
4. Updates kubeconfig for EKS cluster  
5. Applies Kubernetes manifests automatically  

---

## 🐳 Docker
- Application containerized using Docker
- Custom index.html served by NGINX
- Docker image stored securely in Amazon ECR

---

## ✅ Validation

kubectl get pods -n test-app  
kubectl get svc -n test-app  
kubectl get hpa -n test-app  
kubectl get ingress -n test-app  

Access the application using ALB URL:  
http://<ALB-DNS-NAME>

---

## 📌 Outcome
- Scalable and highly available application
- Fully automated CI/CD deployment
- Production-style Kubernetes setup on AWS EKS

---

## 👤 Author
**Saurabh Singh**  
AWS Cloud & DevOps Engineer
