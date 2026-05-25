# Kubernetes WebApp Deployment

## Project Overview

This project demonstrates how to deploy a containerized web application on Kubernetes using Deployment, Service, ConfigMap, Secret, Namespace, Ingress, and PersistentVolumeClaim.

## Tools Used

- Kubernetes
- kubectl
- Minikube
- Docker
- YAML
- NGINX
- Ingress Controller

## Concepts Covered

- Kubernetes Architecture
- Pods
- Deployments
- Services
- ConfigMaps
- Secrets
- Namespaces
- Ingress
- Persistent Volumes
- Scaling
- Rolling Updates
- Auto-healing

## Project Architecture

User → Ingress → Service → Pods → Container

## How to Run

```bash
minikube start
minikube addons enable ingress
kubectl apply -f manifests/
kubectl get all -n dev
```

Access Application

```bash
minikube service webapp-service -n dev
```

Scaling

```bash
kubectl scale deployment webapp-deployment --replicas=4 -n dev
```

Rolling Update

```bash
kubectl set image deployment/webapp-deployment webapp=nginx:1.27 -n dev
kubectl rollout status deployment/webapp-deployment -n dev
```

Auto-healing Test

```bash
kubectl delete pod <pod-name> -n dev
kubectl get pods -n dev
```

## Conclusion

This project helped me understand the complete Kubernetes workflow for deploying, exposing, scaling, updating, and self-healing a containerized web application. It also provided hands-on practice with Kubernetes manifests, namespaces, services, ingress, config maps, secrets, persistent volumes, and rollout management.