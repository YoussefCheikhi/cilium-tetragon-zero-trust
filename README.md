# 🔐 Zero Trust Network with Cilium & Tetragon (eBPF)

## Project Description

**Zero Trust Network with Cilium & Tetragon** is a security-oriented Kubernetes project focused on implementing **Zero Trust principles** at both **network and runtime levels**, using **next-generation eBPF-based technologies**.

The project replaces traditional CNI and runtime security tools with **Cilium** and **Tetragon**, enabling fine-grained **L3–L7 network security**, strong workload identity, encrypted communication, and real-time behavioral detection inside the Kubernetes cluster.

This approach minimizes implicit trust, enforces identity-based access, and enhances observability and threat detection.

---

## 🎯 Project Objectives

1. Replace **Calico** with **Cilium** (Hubble UI included)
2. Enable **automatic mTLS** using **Cilium ClusterMesh**
3. Implement **runtime security detection** with **Tetragon** (partial replacement of Falco)
4. Enforce **L7 Network Policies** (HTTP methods, paths)
5. Use **SPIFFE / SPIRE** for strong workload identities

---

## 🛠️ Technologies Used

- **Kubernetes**
- **Cilium** (eBPF-based CNI)
- **Hubble** (network observability)
- **Tetragon** (eBPF runtime security)
- **SPIFFE / SPIRE**
- **Docker**
- **k3d** (local Kubernetes cluster)

---

## 🧱 Architecture Overview

- **Cilium** acts as the CNI and enforces L3–L7 network policies
- **Hubble** provides real-time observability of network flows
- **Tetragon** monitors runtime behavior using eBPF
- **SPIFFE identities** ensure identity-based access control
- **mTLS** is automatically managed between workloads

---

## ✅ Prerequisites

- Linux / **WSL2** (Ubuntu 22.04+ or 24.04 recommended)
- **Docker** installed and running
- Kubernetes cluster (**k3d recommended**)
- `kubectl` configured
- Cluster admin privileges

---

## 🚀 Quick Start

### 1. Clone the repository

```bash
git clone https://github.com/<your-username>/zero-trust-cilium-tetragon.git
cd zero-trust-cilium-tetragon
