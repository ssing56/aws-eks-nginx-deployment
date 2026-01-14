# AWS EKS NGINX Deployment with HPA and CI/CD

## Overview
This project demonstrates deploying an NGINX application on AWS EKS using Kubernetes best practices.

## Features
- EKS Cluster with managed node group
- Kubernetes Deployment with replicas and resource limits
- ClusterIP Service
- Horizontal Pod Autoscaler (HPA) with CPU target 60%
- AWS Load Balancer Controller with ALB Ingress
- Docker image stored in Amazon ECR
- CI/CD using GitHub Actions (Jenkins pipeline included)

## Architecture
- AWS EKS
- NGINX Deployment (2 replicas)
- HPA
- ALB Ingress
- GitHub Actions CI/CD

## Namespace
- test-app

## CI/CD Flow
1. Code pushed to GitHub
2. Docker image built
3. Image pushed to Amazon ECR
4. Kubernetes manifests applied to EKS

## Note on ALB
ALB creation is blocked due to AWS account-level restriction.
Ingress configuration and AWS Load Balancer Controller setup are completed and verified.
