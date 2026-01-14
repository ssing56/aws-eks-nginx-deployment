# AWS EKS NGINX Deployment with HPA and CI/CD

## Project Overview
This project demonstrates deploying an NGINX application on AWS EKS using Kubernetes best practices. The implementation includes containerization, autoscaling, ingress configuration, and CI/CD automation.

---

## Architecture & Components
- AWS EKS Cluster with managed node group
- Kubernetes Namespace: `test-app`
- NGINX Deployment with resource limits
- ClusterIP / NodePort Service
- Horizontal Pod Autoscaler (HPA)
- AWS Load Balancer Controller with ALB Ingress
- Docker image stored in Amazon ECR
- CI/CD implemented using GitHub Actions (Jenkins pipeline included)

---

## Kubernetes Resources
- **Namespace:** test-app  
- **Deployment:** nginx-deployment (2 replicas)  
- **Service:** nginx-service  
- **HPA:** nginx-hpa (CPU target 60%)  
- **Ingress:** nginx-ingress (AWS ALB)

---

## CI/CD Workflow
On every push to the `main` branch, the CI/CD pipeline performs the following steps:

1. Builds a Docker image for the application  
2. Pushes the image to Amazon ECR  
3. Applies Kubernetes manifests to the EKS cluster  

The pipeline is implemented using **GitHub Actions**.  
A **Jenkins pipeline** is also included for demonstration of an alternative CI/CD approach.

---

## Ingress and Load Balancer
The application is exposed using a Kubernetes Ingress resource configured for the **AWS Load Balancer Controller** with an Application Load Balancer (ALB).

**Note:**  
ALB provisioning is currently blocked due to an AWS account-level restriction.  
The ingress configuration and AWS Load Balancer Controller setup are completed and validated through Kubernetes resources and events.

---

## Summary
- Successfully deployed an NGINX application on AWS EKS  
- Implemented autoscaling using Horizontal Pod Autoscaler  
- Configured ingress using AWS Load Balancer Controller  
- Automated build and deployment using CI/CD pipelines  
- Identified and documented AWS account-level limitations professionally  

---

## Author
**Saurabh Singh**
