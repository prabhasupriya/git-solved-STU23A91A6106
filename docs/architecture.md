# System Architecture

## Overview
DevOps Simulator follows a microservices architecture designed for high availability, scalability, and AI-driven experimental features.

**Development Version**: Used for testing and debugging in a local environment.  
**Experimental Build**: Includes advanced AI, multi-cloud, and chaos engineering features.

---

## Components

### 1. Application Server
- **Technology**: Node.js + Express (with hot reload)
- **Port**: 3000 (development), 9000–9002 (experimental)
- **Scaling**: Manual in dev / AI-powered predictive auto-scaling in experimental
- **Debug**: Chrome DevTools debugger on port 9229
- **Message Queue (Experimental)**: Apache Kafka for event streaming

---

### 2. Database Layer
- **Development**: Local PostgreSQL 14 (single instance)
- **Experimental**: Distributed PostgreSQL 14 cluster (5 nodes)
- **Cache**: Redis (local) / Redis cluster (AI cache optimization)
- **Backup**: Manual (dev) / Continuous with geo-redundancy (experimental)
- **AI Features**: Query optimization, index suggestions

---

### 3. Monitoring System
- **Tool**: Console logging (dev) / Prometheus + Thanos + ELK Stack (experimental)
- **Metrics**: CPU, Memory, Disk, Network, Build time
- **Alerts**: Console warnings (dev) / AI anomaly detection (experimental)
- **Dashboard**: Local web dashboard (in dev)

---

### 4. Container Orchestration
- **Development Tool**: Docker Compose (App + DB + Redis)
- **Experimental Tool**: Kubernetes (multi-cloud orchestration)
- **Supported Clouds**: AWS, Azure, GCP, DigitalOcean
- **Failover**: Automatic cross-cloud failover in experimental mode

---

### 5. Authentication System
- **Method**: OAuth2 + JWT
- **Providers**: Google, GitHub (for testing)
- **Session Storage**: Redis-based
- **Security (Experimental)**: Zero-trust model, AES-256 encryption, audit logging

---

### 6. AI/ML Pipeline (Experimental Only)
- **Frameworks**: TensorFlow, PyTorch, Scikit-learn
- **Models**:
  - Anomaly detection (LSTM)
  - Load prediction (XGBoost)
  - Auto-scaling optimizer (Reinforcement Learning)
- **Training**: Continuous online learning
- **Inference**: Real-time predictions (<50ms)

---

## Deployment Strategy
- **Development**: Docker Compose with hot reload
- **Experimental**: Kubernetes-based deployment with zero downtime
- **Rollback**: Git revert or checkpoint restore

---

## Development Workflow
1. Make code changes  
2. Auto-reload triggers rebuild  
3. Run unit tests  
4. Check console logs  
5. Commit when ready  

---

## Security
- SSL/TLS disabled for local development  
- Database credentials stored in plain text (dev only)  
- CORS enabled for all origins  
- Debug endpoints exposed (dev only)  
- AES-256 encryption and audit logging in experimental mode  

---

## Experimental Features
⚠️ **Warning**: The following features are experimental and may be unstable:
- Multi-cloud deployment  
- AI-powered log analysis  
- Automatic rollback on anomaly detection  
- Chaos engineering simulation  
