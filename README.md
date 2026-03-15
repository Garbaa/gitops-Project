# 🚀 GitOps Kubernetes Cluster with ArgoCD, Prometheus & Grafana

## 🎯 Overview
This project demonstrates a **production-ready Kubernetes cluster** built from scratch using **kubeadm**, managed with **GitOps** principles through **ArgoCD**, and fully monitored with **Prometheus & Grafana**.

## ✨ Key Features
- ✅ **3-node cluster** (1 master, 2 workers) provisioned with Vagrant
- ✅ **Calico CNI** for pod networking
- ✅ **GitOps** with ArgoCD :
  - 🔄 **Auto-sync** – Automatic deployment on Git changes
  - 🗑️ **Auto-prune** – Automatic deletion of removed resources
  - 🛡️ **Self-healing** – Automatic correction of manual changes
- ✅ **Full monitoring** stack (Prometheus, Grafana)
- ✅ **4 sample applications** deployed via ArgoCD
- ✅ **ServiceMonitors** for ArgoCD metrics in Prometheus
- ✅ **RBAC troubleshooting** and resolution

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
```

### 2. Start the cluster
```bash
vagrant up
```

### 3. Access the cluster
```bash
vagrant ssh controlplane
kubectl get nodes
```

### 4. Access ArgoCD UI
```
https://192.168.1.17:30265
```

### 5. Access Prometheus UI
```
https://192.168.1.17:31213
```

### 6. Access Grafana
```
https://192.168.1.17:30697
```
Default credentials: `admin` / `prom-operator`

## 📁 Project Structure

```
gitops-Project/
├── vagrant/
│   ├── Vagrantfile              # 3-node cluster configuration
│   └── scripts/                  # Provisioning scripts
├── declarative/
│   ├── app-of-apps/              # Root ArgoCD application
│   ├── manifests/                 # Application manifests
│   │   ├── geocentric-model/
│   │   ├── heliocentric-model/
│   │   └── heliocentric-model-no-pluto/
│   ├── mono-app/                  # Single application example
│   └── multi-app/                  # Multi-component example
├── .gitignore
└── README.md
```

## 🔄 GitOps Workflow

### Auto-Sync, Auto-Prune & Self-Healing

Each ArgoCD application is configured with:

```yaml
syncPolicy:
  automated:
    prune: true      # Automatically remove deleted resources
    selfHeal: true   # Automatically correct manual changes
```


## 📊 Monitoring Stack

### Integrated Components
- **Prometheus Operator** – Manages Prometheus instances
- **kube-prometheus-stack** – Complete monitoring stack
- **ServiceMonitors** – Custom configurations for ArgoCD
- **Grafana Dashboards** – Pre-configured for Kubernetes & ArgoCD

### Metrics Collected
- ✅ Kubernetes cluster metrics (nodes, pods, kubelet)
- ✅ ArgoCD metrics (applications, sync status, controller performance)
- ✅ Node-level metrics (CPU, memory, disk)


## 🙏 Credits

The sample applications in `declarative/` are based on examples from [sidd-harth](https://github.com/sidd-harth/argocd-example-apps).

### My Contributions
- ✅ Full infrastructure (Vagrant, kubeadm, Calico)
- ✅ GitOps implementation with auto-sync, auto-prune, self-healing
- ✅ Monitoring integration (Prometheus, Grafana)
- ✅ ServiceMonitors for ArgoCD
- ✅ Troubleshooting RBAC and network issues

## 📄 License

This project is licensed under the Apache-2.0 License.

---

## 📬 Contact

**Haythem Garbaa**  
[LinkedIn](linkedin.com/in/haythem-garbaa-491884257) | [GitHub](https://github.com/Garbaa)

---

⭐ If you found this project helpful, please give it a star!





