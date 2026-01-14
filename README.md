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
``bash
kubectl get pods -n test-app
Result

Two NGINX pods running successfully

All pods in Running state

📸 Screenshot:
screenshots/pods-running.png

2. Horizontal Pod Autoscaler (HPA)

Command

kubectl get hpa -n test-app


Result

Target CPU utilization: 60%

Min replicas: 2

Max replicas: 5

Current replicas: 2

📸 Screenshot:
screenshots/hpa-status.png

3. Kubernetes Service

Command

kubectl get svc -n test-app


Result

Service nginx-service exposed on port 80

Service correctly mapped to NGINX pods

📸 Screenshot:
screenshots/service-status.png

4. Ingress Resource (AWS ALB)

Command

kubectl get ingress -n test-app


Result

Ingress created successfully

Ingress class: alb

Routing rules configured

📸 Screenshot:
screenshots/ingress-status.png

5. Ingress Details and ALB Configuration

Command

kubectl describe ingress nginx-ingress -n test-app


Result

ALB annotations applied

Scheme: internet-facing

Target type: ip

Backend service mapped correctly

📸 Screenshot:
screenshots/ingress-describe.png

Important Note:
ALB provisioning is blocked due to an AWS account-level restriction.
However, AWS Load Balancer Controller setup and ingress behavior are verified via Kubernetes events.

6. AWS Load Balancer Controller

Command

kubectl get pods -n kube-system | grep load-balancer


Result

AWS Load Balancer Controller pods running successfully

📸 Screenshot:
screenshots/alb-controller-pods.png

Conclusion

Application successfully deployed on AWS EKS

Autoscaling implemented using HPA

Ingress configured using AWS Load Balancer Controller

CI/CD pipeline automates build and deployment

ALB restriction identified and documented professionally

Author

Saurabh Singh
```bash
kubectl get pods -n test-app
