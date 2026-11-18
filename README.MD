# 🚀 RoboShop – Microservices Deployment on Kubernetes

## 📌 Project Overview

This project demonstrates the deployment of a containerized **RoboShop e-commerce application** using Kubernetes.

RoboShop follows a microservices architecture where individual application components run as independent services. Kubernetes manages the application workloads, service communication, and container orchestration.

The project includes multiple application microservices along with supporting databases, caching, and messaging components.

## 🏗️ Architecture

The application consists of the following components:

| Component | Responsibility |
|---|---|
| Frontend | User interface |
| Catalogue | Product catalogue management |
| Cart | Shopping cart management |
| User | User management |
| Payment | Payment processing |
| Shipping | Shipping management |
| MongoDB | NoSQL database |
| MySQL | Relational database |
| Redis | In-memory caching |
| RabbitMQ | Message queuing |

### Application Architecture

```text
                 USER
                   |
                   v
               FRONTEND
                   |
          -------------------
          |        |        |
          v        v        v
       CATALOGUE  CART     USER
          |        |        |
          v        v        v
       MongoDB   Redis    MongoDB
                   |
                   v
                PAYMENT
                   |
                   v
                RabbitMQ
                   |
                   v
                SHIPPING
                   |
                   v
                 MySQL
```

*Note: This is a conceptual application flow, not a representation of verified Kubernetes networking or every service dependency.*

## 🛠️ Technology Stack

- **Containerization:** Docker
- **Container Orchestration:** Kubernetes
- **Cluster Management:** kubectl
- **Container Registry:** As configured in the deployment manifests
- **Application Architecture:** Microservices
- **Databases:** MongoDB, MySQL
- **Caching:** Redis
- **Messaging:** RabbitMQ

## 📂 Repository Structure

```text
k8s-roboshop/
│
├── Shipping/
├── cart/
├── catalogue/
├── debug/
├── frontend/
├── mongodb/
├── mysql/
├── payment/
├── rabbitmq/
├── redis/
└── user/
```

Each service directory contains its respective project configuration and deployment-related files.

## 🚀 Deployment Guide

### 1. Clone the Repository

```bash
git clone https://github.com/surya-phani-teja/k8s-roboshop.git

cd k8s-roboshop
```

### 2. Verify Kubernetes Cluster

```bash
kubectl get nodes

kubectl cluster-info
```

### 3. Deploy Application Components

Apply the Kubernetes YAML manifests from their respective service directories.

Example:

```bash
kubectl apply -f <path-to-frontend-manifests>
kubectl apply -f <path-to-mongodb-manifests>
kubectl apply -f <path-to-redis-manifests>
```

Repeat for the remaining application components, following their dependencies.

### 4. Verify Deployments

Check the deployed workloads:

```bash
kubectl get deployments -A

kubectl get pods -A

kubectl get services -A

kubectl get nodes
```

### 5. Troubleshooting

Inspect pod details:

```bash
kubectl describe pod <pod-name>
```

Check application logs:

```bash
kubectl logs <pod-name>
```

Check cluster events:

```bash
kubectl get events --sort-by=.metadata.creationTimestamp
```

## 🔍 Key Kubernetes Concepts

This project provides practical exposure to:

- Microservices deployment
- Kubernetes Deployments and Pods
- Kubernetes Services and service discovery
- Container orchestration
- Inter-service communication
- Database and caching integration
- Message queue integration
- Application troubleshooting
- Kubernetes resource monitoring

## 🎯 Project Objective

The objective of this project is to understand how a real-world microservices-based application can be deployed and managed using Kubernetes.

It demonstrates the practical implementation of container orchestration and the deployment of distributed application components.

## 👨‍💻 Author

**Surya Phani Teja**

GitHub: [surya-phani-teja](https://github.com/surya-phani-teja)

Project: [K8s RoboShop](https://github.com/surya-phani-teja/k8s-roboshop)