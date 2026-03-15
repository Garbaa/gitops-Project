# 🚀 GitOps Kubernetes Cluster with ArgoCD, Prometheus & Grafana

 ## 🎯 Overview
This project demonstrates a **production-ready Kubernetes cluster** built from scratch using **kubeadm**, managed with **GitOps** principles through **ArgoCD**, and fully monitored with **Prometheus & Grafana**.

#✨ Key Features
    - ✅ **3-node cluster** (1 master, 2 workers) provisioned with Vagrant
    - ✅ **Calico CNI** for pod networking
    - ✅ **GitOps** with ArgoCD (auto-sync, auto-prune, self-healing)
    - ✅ **Full monitoring** stack (Prometheus, Grafana, Alertmanager)
    - ✅ **4 sample applications** deployed via ArgoCD
    - ✅ **ServiceMonitors** for ArgoCD metrics in Prometheus
    - ✅ **RBAC troubleshooting** and resolution
    - ✅ **Self-healing** demonstrations

## 🏗️ Infrastructure Details

- **Master Node**: controlplane (192.168.1.17) – 6GB RAM
- **Worker Nodes**: node01 (192.168.1.20) & node02 (192.168.1.21) – 3GB RAM each
- **Network**: Bridge mode for external access
- **OS**: Ubuntu 22.04 LTS

## 📦 Prerequisites

- [Vagrant](https://www.vagrantup.com/downloads) 2.4+
- [VirtualBox](https://www.virtualbox.org/wiki/Downloads) 7.0+
- 8GB+ RAM recommended
- GitHub account

## ⚡ Quick Start

### 1. Clone the repository
```bash
git clone https://github.com/Garbaa/gitops-Project.git
cd gitops-Project/vagrant


