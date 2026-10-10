# Project 1: Container Orchestration with Kubernetes

**Internship:** Rhombix Technologies, DevOps Domain

## Overview

This project deploys a simple nginx web application on a local Kubernetes cluster
using Minikube (Docker driver). It demonstrates:

- Creating a **Deployment** (manages Pods)
- Exposing the app with a **Service** (load balancing across Pods)
- **Scaling** the application up and down
- **Self-healing** (Kubernetes recreates a deleted Pod automatically)

## Prerequisites

- Docker
- Minikube
- kubectl

Start the cluster and verify:

```bash
minikube start --driver=docker
kubectl get nodes
```

## Project Structure

## Steps

### 1. Deploy the application

```bash
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
```

### 2. Verify Pods, Deployment and Service

```bash
kubectl get pods
kubectl get deployments
kubectl get services
```

### 3. Access the application

```bash
minikube service my-app-service
```

This opens the nginx welcome page in the browser.

### 4. Scale up (2 to 5 replicas)

```bash
kubectl scale deployment my-app --replicas=5
kubectl get pods
```

### 5. Scale down (5 to 2 replicas)

```bash
kubectl scale deployment my-app --replicas=2
kubectl get pods
```

### 6. Self-healing demo

```bash
kubectl get pods
kubectl delete pod <pod-name>
kubectl get pods
```

Kubernetes automatically creates a new Pod to keep the desired replica count of 2.

## Screenshots

All screenshots of the cluster, deployment, scaling and self-healing are in the
`screenshots/` folder.

## What I Learned

- How Deployments keep a desired number of Pods running
- How Services provide a stable endpoint and load balance traffic
- How easily Kubernetes scales applications and recovers from Pod failure

## Video Explanation

(Link to the LinkedIn video post)
