# Automating Persistent Volumes for MariaDB with OpenTofu

This project demonstrates how to automate the provisioning of Persistent Volumes (PV) and Persistent Volume Claims (PVC) for MariaDB using **OpenTofu** and deploy it into a Kubernetes cluster.  
The goal of this automation is to ensure that MariaDB has **persistent, durable, and reliable storage** regardless of Pod restarts, rescheduling, or failures within the Kubernetes cluster.

---

## 📦 Project Overview

Managing persistent data for stateful applications like MariaDB can be challenging in Kubernetes.  
This project uses:

- **OpenTofu** → Infrastructure as Code (IaC) to automate Kubernetes resources  
- **MariaDB** → Database engine that requires persistence  
- **Kubernetes PVC & PV** → Persistent storage for database workloads  
- **Kubernetes Secret** → Manage database credentials securely  
- **StorageClass** → Define volume provisioning strategy  

OpenTofu automates the creation of all required Kubernetes manifests such as:

- Namespace  
- Secrets  
- Persistent Volume  
- Persistent Volume Claim  
- MariaDB Deployment  
- MariaDB Service  

This reduces human error and ensures reproducible infrastructure deployment.

---

## 🚀 Architecture
OpenTofu ─┬─> Creates Secret (DB Password)
├─> Creates PersistentVolumeClaim
├─> Creates PersistentVolume
├─> Deploys MariaDB Deployment
└─> Deploys MariaDB ClusterIP Service

