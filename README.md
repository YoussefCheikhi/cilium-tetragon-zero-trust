# cilium-tetragon-zero-trust
Zero Trust Network with Cilium & Tetragon (eBPF)
Project Description

Zero Trust Network with Cilium & Tetragon is a security-oriented Kubernetes project focused on implementing Zero Trust principles at both network and runtime levels, using next-generation eBPF-based technologies.

The project replaces traditional CNI and runtime security tools with Cilium and Tetragon, enabling fine-grained L3–L7 network security, strong workload identity, encrypted communication, and real-time behavioral detection inside the Kubernetes cluster.

This approach minimizes implicit trust, enforces identity-based access, and enhances observability and threat detection.

Project Objectives

Replace Calico with Cilium (Hubble UI included)

Enable automatic mTLS using Cilium ClusterMesh

Implement runtime security detection with Tetragon (partial replacement of Falco)

Enforce L7 Network Policies (HTTP methods, paths)

Use SPIFFE/SPIRE for strong workload identities

Technologies Used

Kubernetes

Cilium (eBPF-based CNI)

Hubble (Network Observability)

Tetragon (eBPF Runtime Security)

SPIFFE / SPIRE

Docker

k3d (local Kubernetes cluster)

Architecture Overview

Cilium acts as the CNI and enforces L3–L7 network policies

Hubble provides real-time observability of network flows

Tetragon monitors runtime behavior using eBPF

SPIFFE identities are used for identity-based security

mTLS is automatically managed between workloads

Prerequisites

Linux / WSL2 (Ubuntu 22.04+ or 24.04 recommended)

Docker installed and running

Kubernetes cluster (k3d recommended)

kubectl configured

Cluster admin privileges

Quick Start
1. Clone the repository
git clone https://github.com/<your-username>/zero-trust-cilium-tetragon.git
cd zero-trust-cilium-tetragon

2. Create the Kubernetes cluster (k3d)
k3d cluster create mycluster --servers 1 --agents 2
export KUBECONFIG=$(k3d kubeconfig write mycluster)
kubectl get nodes

3. Install Cilium with Hubble
cilium install --enable-hubble
cilium status

4. Deploy Tetragon
kubectl apply -f https://raw.githubusercontent.com/cilium/tetragon/main/install/kubernetes/tetragon.yaml

5. Apply Zero Trust Network Policies

See the policies under the policies/ directory.

Repository Structure
zero-trust-cilium-tetragon/
├── docs/                # Concepts, architecture, step-by-step guides
├── policies/            # Cilium Network Policies (L3–L7)
├── scripts/             # Automation and setup scripts
├── manifests/           # Kubernetes manifests
├── screenshots/         # Proof and validation screenshots
├── README.md            # Project documentation
└── LICENSE              # License information

Validation & Observability

kubectl get pods -A

cilium status

hubble observe

Tetragon alerts via kubectl logs

Screenshots and outputs are available in the screenshots/ directory.

Project Status

🚧 Work in progress
Planned next steps:

Full SPIRE integration

Advanced runtime rules with Tetragon

Multi-cluster Zero Trust using ClusterMesh

Contributors

Youssef Cheikhi

Project partner: Security & Cloud specialization

Contributions are welcome via issues and pull requests.

License

This project is released under the MIT License.
