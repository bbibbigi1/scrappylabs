# 🪐 Scrappylabs Environment Master Blueprint

A production-grade architecture map detailing how a mishmash of spare hardware, clever workarounds, and pure determination were transformed into a secure, enterprise-ready playground. Welcome to the madness driving the `scrappylabs` ecosystem!

---

## 🎛️ Network Segmentation Layout (VLAN Matrix)
Our local traffic fabric is structurally split into distinct zones, keeping casual web surfers far away from our core laboratory operations:

* **Core Infrastructure & Admin Tier:** `10.0.1.X`
* **Isolated Client Tier (User PCs):** `10.0.10.X`
  * Dedicated Workstation Allocation: `10.0.10.X`
* **Application & Service Compute Tier:** `10.0.14.X`

---

## ⚙️ Core Management Interface Matrix
The main control rooms keeping our network equipment behaving and orchestrating our virtualization layers:

### 1. Edge Firewall Security Gateway
* **Core Appliance Host:** `OPNSense Routing Gateway`
* **Internal Network Address:** `10.0.1.X`
* **Access Control Mapping:** Secured via unique administrative IAM profiles.

### 2. Physical Network Switching Core
* **Core Appliance Host:** `Managed Layer 2 Switch`
* **Internal Network Address:** `10.0.1.X`

### 3. Base Virtualization Hypervisor
* **Core Appliance Host:** `Proxmox VE Cluster Management Console`
* **Internal Network Address:** `10.0.1.X:8006`
* **Access Control Mapping:** Enforced under hardened cryptographic credential layers.

---

## 📦 Localized Application Compute Tier (`10.0.14.X`)
Central application services corralled across modular virtual containers:

### 🖥️ Compute Group A: Infrastructure Monitoring VM
* **Management Engine Host Node:** `10.0.14.X`
* **Service Integrations:**
  * `10.0.14.X:7575` — Unified Application Control Panel Panel (`homarr`)
  * `10.0.14.X:80` / `/admin/` — Upstream Local Caching DNS Resolver
  * `10.0.14.X` — Isolated Game Server Hosting Sandbox 
  * `10.0.14.X` — Encrypted Tailscale Subnet Router Gateway Mesh Node
* **Access Control Mapping:** Isolated using split administrative credentials and strict guest-level access profiles.

### ☁️ Compute Group B: Self-Hosted Cloud Services VM
* **Cloud Services Host Node:** `10.0.14.X`
* **Service Integrations:**
  * `10.0.14.X:2283` — High-Performance Photo Management Stack (`Immich`)
  * `10.0.14.X:9495` — Multi-User Web-Native Filesystem Browser
  * `10.0.14.X:8384` — Peer-to-Peer Decentralized File Sync Engine (`Syncthing`)
  * `10.0.14.X:8010` — Document Lifecycle Ecosystem (`Paperless-ngx`)
  * `10.0.14.X:8083` — Server-Side PDF Editing Engine
* **Access Control Mapping:** Managed via isolated role-based access levels (Administrator, Developer, Client).

---

## 🌐 Ingress Edge & Service Routing Configuration
External overlay domains mapping into internal resources. All active routes are obfuscated via local path rules and zero-trust proxies to mask our physical network's identity from the outside world:

* **Unified Application Dashboard:** `https://example.com`
* **Secure Encrypted Password Vault:** `https://example.com`
* **Local DNS Resolver Panel:** `https://example.com`
* **Telemetry Monitoring Infrastructure Engine:** `https://example.com`
* **Edge Entertainment Host Endpoint:** `https://example.com`
