# Kubernetes Cluster Health Checker & Auto-Healing System

## 📌 Project Overview

This project focuses on building an automated monitoring and self-healing system for Kubernetes clusters. It helps DevOps teams maintain high availability by continuously monitoring cluster health, detecting failures, and automatically resolving common issues.

---

## 🎯 Objectives

* Monitor Kubernetes cluster health (nodes, pods, resources)
* Detect failures and anomalies in real time
* Implement self-healing mechanisms (pod restart, rescheduling, scaling)
* Provide alerts via Slack/Alertmanager
* Visualize metrics using Grafana dashboards

---

## 🏗️ Architecture Overview

Components involved:

* Kubernetes Cluster (Minikube / AKS / Kind)
* Health Checker Service (Python/Go)
* Prometheus (metrics collection)
* Grafana (visualization)
* Alertmanager (alerts)
* Slack API (notifications)

---

## 🛠️ Tech Stack

| Tool         | Purpose                 |
| ------------ | ----------------------- |
| Kubernetes   | Container orchestration |
| Python / Go  | Health checker logic    |
| Prometheus   | Metrics collection      |
| Grafana      | Dashboard visualization |
| Alertmanager | Alert routing           |
| Docker       | Containerization        |

---

## 📂 Project Structure (Initial)

```
k8s-health-checker/
│
├── src/
│   ├── health_checker.py
│   ├── auto_healer.py
│   └── utils/
│
├── k8s-manifests/
│   ├── deployment.yaml
│   ├── service.yaml
│   └── rbac.yaml
│
├── monitoring/
│   ├── prometheus/
│   └── grafana/
│
├── docker/
│   └── Dockerfile
│
├── scripts/
│   └── setup.sh
│
└── README.md
```

---

## 🚀 Setup Guide (Sprint 1)

### 1. Prerequisites

Ensure the following tools are installed:

* kubectl
* Docker
* Minikube / Kind (or access to AKS/EKS)
* Python 3.x or Go

---

### 2. Start Kubernetes Cluster

Using Minikube:

```
minikube start
```

Verify cluster:

```
kubectl get nodes
```

---

### 3. Configure Kubernetes Access

Check cluster connectivity:

```
kubectl cluster-info
```

---

### 4. Setup Prometheus (Monitoring)

Using Helm:

```
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo update
helm install prometheus prometheus-community/prometheus
```

Verify:

```
kubectl get pods
```

---

### 5. Setup Grafana

```
helm install grafana prometheus-community/grafana
```

Get admin password:

```
kubectl get secret --namespace default grafana -o jsonpath="{.data.admin-password}" | base64 --decode
```

---

### 6. Run Health Checker (Initial)

Install dependencies:

```
pip install kubernetes
```

Run script:

```
python src/health_checker.py
```

---

## 🔍 Features (Planned by Sprints)

### Sprint 1

* Kubernetes cluster setup
* API access
* Prometheus integration

### Sprint 2

* Node & pod health monitoring
* Metrics visualization
* Basic alerting

### Sprint 3

* Pod auto-healing
* CrashLoopBackOff handling

### Sprint 4

* Auto scaling (HPA)
* Resource balancing

### Sprint 5

* Slack notifications
* Advanced alert rules

### Sprint 6

* Dashboard enhancements
* Documentation

---

## 📊 Expected Deliverables

* Automated health monitoring system
* Self-healing mechanisms
* Alerting system
* Grafana dashboard
* Complete documentation

---

## 💰 Cost Optimization Strategy

* Use resource limits and requests
* Implement auto-scaling
* Scale down idle resources

---

## 🧪 Future Enhancements

* AI-based anomaly detection
* Multi-cluster monitoring
* Integration with cloud-native tools

---

## 🤝 Contribution

Contributions are welcome. Please fork the repository and create a pull request.

---

## 📄 License

This project is for educational purposes.


Thanks 
