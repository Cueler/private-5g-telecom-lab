# 📡 Private 5G Telecom Lab - Infrastructure & Core Validation Bench

![Private 5G SA Topology Baseline](./screenshots/5g-sa-infrastructure-final.png)

Welcome to the continuous validation repository for the Private 5G Standalone (SA) Telecom Laboratory. This space is engineered exclusively to host raw environment proofs, system logs, and live session verifications across the entire virtualized network fabric.

> ⚠️ **CRITICAL LIFECYCLE DECLARATION:**
> The documentation and chapters hosted within this repository serve strictly as **runtime evidence and proof-of-concept (POC) validations of the current active laboratory status**. The definitive production-grade Git infrastructure, automation scripts, and deployment configurations are actively under construction. Repository elements and code bases will be incrementally released and injected as internal academic and applied research modules advance.

---

## 🏗️ Virtualization & Subsystem Architecture Mapping

The environment is deployed over an enterprise Type-1 Hypervisor topology (Proxmox VE), leveraging strict resource isolation via optimized Linux Containers (LXC) and Virtual Machines to isolate control, security, telemetry, and user plane functions:

| Component ID | Hostname / Node Function | Network Assignment | Current Lifecycle Phase |
| :--- | :--- | :--- | :--- |
| **CT 200** | MikroTik RouterOS Core Gateway | Upstream Loop | Operational (Edge Boundary Enabled) |
| **CT 104** | Host Software Bridge Interconnect | Multi-Bridge L2 | Operational (Bridge Loop Active) |
| **CT 100** | pfSense Next-Gen Virtual Firewall | `10.0.0.1` | Operational (Perimeter Screen Online) |
| **CT 101** | Zabbix Server Enterprise Engine | `10.0.0.163` | Framework Active (Engines in Backlog) |
| **CT 102** | Timeseries DB & Local Grafana | `10.0.0.164` | Framework Active (Dashboards Under Design) |
| **SaaS** | Hybrid Grafana Cloud Extender | Remote Cluster | Active Telemetry (Stream Testing) |
| **CT 103** | Open5GS 5G Core Network Core | `10.0.0.170` | Operational (3GPP Daemons Active) |
| **CT 106** | UERANSIM RAN Emulation Node | `10.0.0.171` | Operational (SCTP Interface Online) |

---

## 📚 Active Validation Chapters & Telemetry Evidence

Each module below anchors the technical specifications, architectural essence, and unedited live streaming verifications validating container runtime loops:

### 🌐 [Chapter 1: Hypervisor Isolation & Boundary Routing](./documentation/validations/CHAPTER_1_EDGE_ROUTING.md)
* Enforces Layer-2 and Layer-3 hardware abstraction boundaries.
* **Live Proofs:** [MikroTik RouterOS Boot Verification](https://streamable.com/1wmmw0) | [Winbox Interface Session](https://streamable.com/xzlkd0) | [Bridge Initialization](https://streamable.com/0b9js2).

### 🛡️ [Chapter 2: Perimeter Security & Stateful Firewall (NGFW)](./documentation/validations/CHAPTER_2_PERIMETER_SECURITY.md)
* Validates access control matrices, core NAT mechanisms, and user plane subnet isolation.
* **Live Proof:** [pfSense Container Status & Administrative Web UI Interaction](https://streamable.com/ujexvg).

### 📊 [Chapter 3: Unified Telemetry & Hybrid Cloud Observability](./documentation/validations/CHAPTER_3_INFRASTRUCTURE_OBSERVABILITY.md)
* Tracks baseline system health states and remote cloud data streaming parameters.
* **Live Proofs:** [Zabbix Core Activation](https://streamable.com/emlxcq) | [Local Grafana Web Console](https://streamable.com/nfocnh) | [Grafana Cloud Host Telemetry](https://streamable.com/q217ys).

### 🧠 [Chapter 4: 5G Standalone Core Network & RAN Emulation](./documentation/validations/CHAPTER_4_5G_CORE_NETWORKING.md)
* Anchors 3GPP Release 16 protocol stacks, AMF/SMF/UPF runtime state tables, and emulated radio bearer attachment loops.
* **Live Proofs:** [Open5GS Core Daemons Initialization](https://streamable.com/ribyg7) | [Subscriber Provisioning Web Console](https://streamable.com/b4vl7b) | [UERANSIM Micro-Service Startup](https://streamable.com/rbzdif) | [gNodeB Connection & Active UE Handshake](https://streamable.com/59jery).

---
*Developed by César Ueler | Telecommunications Infrastructure & Cyber Security Research Lab.*
