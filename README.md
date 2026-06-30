# 🛠️ Welcome to scrappylabs!

An overview of a high-uptime, multi-user infrastructure designed for stability, data isolation, and secure, containerized operations.

> 👥 **Operational Status**: This infrastructure acts as a private production environment serving a dedicated multi-user base. This deployment scenario enforces strict production requirements for high uptime, service stability, structured change-management maintenance windows, and absolute user-data isolation across all active service boundaries.

---

## 🗺️ Visual Network Topology
View the system structure:
![Scrappylabs Network Topology](/home/bbibbigi/Documents/lab_stuff/Homelab_Documents/diagrams/network_logic_v1.png)

---

## 📚 Core Architecture & Engineering Highlights

* **Virtualization & AI**: Managed Proxmox VE nodes with isolated, high-performance Ollama AI inference pipelines.
* **Network & Security**: Tailscale (WireGuard) mesh networking for encrypted, direct host-to-host connectivity, eliminating exposed public firewall ports.
* **Infrastructure Management**: Multi-instance setup with secure, unique cryptographic keys for user isolation.

---

## 🚀 Architectural Backlog & Future Roadmap

To scale this infrastructure, the following milestones are planned:

### 1. High Availability & System Redundancy
* **🔄 HA Failover Cluster**: Implementing multi-node Proxmox VE/Ceph to eliminate single points of failure.
* **📡 Traffic Management**: Deploying active-passive reverse proxy failover (OPNsense CARP/HAProxy) for seamless maintenance transitions.

### 2. Media Pipeline & Storage
* **🎬 Media Lifecycle**: Deploying a containerized stack utilizing Jellyfin for streaming and Sonarr for automated ingestion.
* **💾 Centralized NAS**: Implementing a dedicated ZFS-based storage array (TrueNAS) for reliable media pooling and VM/container snapshots.

### 3. AI Sandboxing & Automation
* **🤖 Isolated AI Sandbox**: A strictly firewalled staging container for testing custom AI agents and local fine-tuning experiments.
* **💻 Scripting Framework**: Developing a centralized repository for custom Bash/Python utility scripts to automate configuration and maintenance.

### 4. Security & Monitoring
* **🛡️ Zero-Trust Security**: Transitioning to Cloudflare Access and strict reverse proxy controls.
* **📈 Observability**: Implementing Prometheus/Grafana to monitor hardware health and network traffic across the Tailscale mesh.
