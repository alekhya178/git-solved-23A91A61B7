# System Architecture

## Overview
DevOps Simulator follows a microservices architecture designed for high availability and scalability.  
This document covers **production**, **development**, and **experimental** configurations.

---

## Components

### 1. Application Server
- **Technology**: Node.js + Express
- **Production Port**: 8080
- **Development Port**: 3000
- **Scaling**: Horizontal auto-scaling (production only)
- **Development Features**: Hot reload, debug mode

### 2. Database Layer
- **Database**: PostgreSQL 14
- **Production**: Master-slave replication with automated backups
- **Development**: Single local instance with seed data

### 3. Monitoring System
- **Production**: Prometheus + Grafana with email alerts
- **Development**: Console logging with verbose output
- **Metrics**: CPU, Memory, Disk, Network

---

## Deployment Strategy

### Production
- **Method**: Rolling updates  
- **Zero-downtime**: Yes  
- **Rollback**: Automated on failure  
- **Region**: us-east-1  

### Development
- **Method**: Docker Compose  
- **Features**: Hot reload, instant feedback  
- **Testing**: Automated tests before deployment  

---

## Security
- **Production**: SSL/TLS encryption, strict access controls  
- **Development**: Relaxed security for easier debugging  

---

## Experimental Architecture Additions (from conflict-simulator)

### Overview
The experimental build introduces an **event-driven microservices architecture** with **AI/ML integration** designed for **multi-cloud** and **chaos engineering**.

⚠️ **Note:** This setup is under testing and not yet production-ready.

### 1. AI-Enhanced Application Server
- **Technology**: Node.js + Express + TensorFlow.js  
- **Ports**: 9000 (main), 9001 (metrics), 9002 (AI API)  
- **Scaling**: AI-powered predictive auto-scaling  
- **Queue**: Apache Kafka for event streaming  

### 2. Distributed Database Layer
- **Database**: PostgreSQL 14 cluster (5 nodes)  
- **Cache**: Redis cluster with ML-based optimization  
- **Backup**: Continuous with geo-redundancy  
- **AI Features**: Query optimization, index suggestions  

### 3. AI/ML Pipeline
- **Frameworks**: TensorFlow, PyTorch, Scikit-learn  
- **Models**:  
  - LSTM-based anomaly detection  
  - XGBoost load prediction  
  - Reinforcement Learning for auto-scaling  
- **Latency**: Real-time inference <50ms  

### 4. Multi-Cloud Orchestration
- **Clouds Supported**: AWS, Azure, GCP, DigitalOcean  
- **Orchestration**: Kubernetes with custom CRDs  
- **Failover**: Automatic cross-cloud  

### 5. Advanced Monitoring & Observability
- **Metrics**: Prometheus + Thanos  
- **Logs**: ELK Stack with AI log analysis  

---

## Summary
This document merges both **stable production/development** architecture and the **experimental AI-driven** extension.  
All experimental components can be toggled via environment variable:  
```bash
export EXPERIMENTAL_MODE=true
