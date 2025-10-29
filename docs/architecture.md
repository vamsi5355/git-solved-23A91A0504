# System Architecture

## Overview
DevOps Simulator follows a **microservices architecture** designed for high availability and scalability.  
This document covers both **production** and **development** configurations.  
Experimental features are documented separately and not production-ready.

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

## ⚙️ Experimental Architecture (For Testing Only)

> The following section describes experimental features from the `instructor/conflict-simulator` branch.  
> These are **not production-ready** and are disabled by default.

### Experimental Overview
DevOps Simulator (Experimental Build) introduces an **event-driven microservices architecture** with **AI/ML integration**, built for **multi-cloud** environments and **chaos engineering** testing.

### Experimental Core Enhancements
- **AI-Enhanced Application Server**
  - Node.js + Express + TensorFlow.js
  - Predictive auto-scaling & real-time inference
  - Kafka for event-driven communication

- **Distributed Database Layer**
  - PostgreSQL 14 Cluster (5 nodes)
  - Redis caching with ML-based optimization
  - Continuous geo-redundant backup

- **AI/ML Pipeline**
  - Frameworks: TensorFlow, PyTorch, Scikit-learn
  - Models: anomaly detection, load prediction, RL-based scaling
  - Continuous online learning & <50ms inference latency

- **Multi-Cloud Orchestration**
  - Supported Clouds: AWS, Azure, GCP, DigitalOcean
  - Kubernetes CRDs with global GeoDNS load balancing
  - Auto failover across regions

- **Advanced Monitoring**
  - Prometheus + Thanos for long-term metrics
  - ELK Stack + AI-based log analysis
