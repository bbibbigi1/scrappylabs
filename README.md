# 🪐 Multi-User Enterprise Homelab Infrastructure

An architecture-focused overview outlining a self-hosted, multi-node infrastructure designed for high-performance virtualization monitoring, secure overlay mesh networking, and containerized local artificial intelligence applications.

> 👥 **Operational Status**: This infrastructure acts as a private production environment serving a dedicated multi-user base. This deployment scenario enforces strict production requirements for high uptime, service stability, structured change-management maintenance windows, and absolute user-data isolation across all active service boundaries.

---

## 🏗️ Core Architecture & Engineering Highlights

*   **Virtualization Hypervisor Stack**: Managed local compute clusters (Proxmox VE nodes) hosting containerized enterprise environments optimized for absolute service isolation.
*   **Decoupled Machine Learning Pipeline**: High-performance AI processing backends executing Ollama inference pipelines, architecturally isolated from frontend user-interface nodes to optimize system compute distribution.
*   **Secure Overlay Fabric**: Integrated Tailscale (WireGuard) mesh network connectivity enabling absolute host-to-host routing encryption, completely bypassing the need to expose public edge router hardware firewall ports.
*   **Granular Authentication Matrix**: Multi-instance host connections mapped securely to isolated, unique Ed25519 cryptographic identity keys managed dynamically via a `lazyssh` TUI orchestration proxy framework.

---

## 📁 Repository Directory Architecture

```text
lab_stuff/
├── .ssh/
│   └── config                  # Active configuration backend file parsed natively by OpenSSH
├── Homelab_Documents/          # Sanitized architecture documentation tracking folder
│   └── network_blueprint.txt   # Generalized mapping tracking DHCP leases and container layouts
├── .gitignore                  # Security shield blocking private encryption keys and raw log data files
└── README.md                   # Central infrastructure documentation index and deployment guide
```

---

## ⚙️ Core Infrastructure Map

1.  **Phie Frontend Hub (`phie-web`)**
    *   *Network Topology Scope*: Private Lan Segment `[Internal Subnet IP]`
    *   *Operational Profile*: Orchestrates the containerized Open WebUI stack to serve accessible, interactive dashboard interfaces to local network client users.
2.  **Model File Compute Backend (`phie-files`)**
    *   *Network Topology Scope*: Encrypted WireGuard Overlay Tunnel `[Overlay Network IP]`
    *   *Operational Profile*: High-performance core hosting LLM weight storage and processing raw Ollama inference pipelines securely over WireGuard overlay layers.
3.  **Local Test Cloud Node (`local-cloud`)**
    *   *Network Topology Scope*: Private Lan Segment `[Internal Subnet IP]`
    *   *Operational Profile*: General virtualization testbed sandbox initialized to prototype cloud services, deploy test kernels, and isolate short-term sandbox containers.

---

## 🗺️ Architectural Backlog & Future Roadmap

To scale this infrastructure into an enterprise-grade, fault-tolerant deployment, the following milestones are slated for implementation:

### 1. High Availability & Fault Tolerance
*   **🔄 High Availability (HA) Failover Cluster**: Introduce a multi-node hypervisor cluster (via Proxmox VE/Ceph) to eliminate single points of failure and establish seamless container migration if a core host goes offline.
*   **📡 Load Balancing & Traffic Redundancy**: Implement an active-passive reverse proxy failover loop (via OPNsense CARP or HAProxy virtual IPs) to dynamically route incoming traffic to a secondary standby node during primary server maintenance events.

### 2. Media Pipeline & Network Storage (Slated Next)
*   **🎬 Automated Media Delivery Lifecycle**: Provision a decoupled containerized stack featuring Jellyfin for hardware-accelerated media streaming, coupled with Sonarr/Radarr pipelines for automated content ingestion, metadata indexing, and lifecycle management.
*   **💾 Centralized Network-Attached Storage (NAS) Matrix**: Deploy a dedicated storage array (TrueNAS Core/Scale or a custom ZFS pool) acting as a secure, high-throughput network share. This will serve as a unified, redundant storage target for media pools, raw logs, and Proxmox container state snapshots.

### 3. Security, Monitoring & Automation
*   **🛡️ Isolated Script Sandbox Environment**: Establish a strictly firewalled, non-privileged staging container to act as a secure testing sandbox. This will isolate untrusted scripts, cron-driven automation pipelines, and experimental shell configurations from the rest of the production homelab network.
*   **📈 Centralized Observability Matrix**: Integrate Prometheus, Grafana, and an alerting gateway to monitor hardware thermal baselines, host uptime heartbeats, and network link bandwidth anomalies across all active Tailscale mesh nodes.
