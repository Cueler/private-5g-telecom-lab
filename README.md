# 📡 Private 5G Standalone (SA) Core Network & Advanced Infrastructure Showcase

## 📝 Executive Overview
This repository serves as a public portfolio of technical and operational evidences demonstrating the successful deployment, orchestration, and validation of a private **5G Standalone (SA)** cellular network architecture. 

The entire ecosystem was designed and provisioned using enterprise-grade infrastructure concepts, utilizing lightweight virtualization via **Linux Containers (LXC)** over a **Proxmox VE** hypervisor. Perimeter security, network isolation, and routing optimization were strictly enforced through specialized virtual appliances (**pfSense & MikroTik**), simulating a real-world critical mission industrial network environment.

---

## 🏗️ High-Level Technical Pillars

### 1. Virtualized 5G Standalone Core
* **Core Network Stack:** Implemented using a 3GPP Release 16 compliant open-source cellular core framework (**Open5GS**).
* **Service Decoupling:** Full isolation of network functions in the control plane and user plane, including AMF (Access and Mobility Management Function) and UPF (User Plane Function) daemons running as native system services.

### 2. RAN Simulation & Control/User Plane Handshake
* **Emulated Infrastructure:** Orchestrated via advanced emulation layers (**UERANSIM**) simulating Next-Generation NodeB (gNB) radio stations and User Equipment (UE).
* **Signaling Protocols:** Validation of secure SCTP associations over port `36412` (NGAP layer) and robust GTP-U encapsulation tunnels for subscribers' data plane traffic.

### 3. Unified Telemetry & Observability Layer
* **Metrics Harvesting:** Live monitoring integration utilizing enterprise collectors (**Zabbix / Prometheus Exporters**).
* **Data Visualization:** Production-ready dashboards hosted in **Grafana**, mapping hardware resource constraints, network throughput, and packet-forwarding metrics simultaneously.

---

## 🎬 Operational Evidences & Live Validations

The sections below contain verified, unedited captures of the environment in full production state, validating the architectural stability, orchestration workflow, and routing.

### 🌐 Unified Infrastructure Topology (Validated with Real-time Telemetry)
Below is the validated technical blueprint used to orchestrate this standalone private network. This topology maps the exact container IDs (CT) and internal IPs verified side-by-side with our infrastructure logs:

![Validated Infrastructure Blueprint](screenshots/5g-sa-infrastructure-final.png)

### 🖥️ Proxmox VE Boot Sequence & E2E Core 5G SA Operation Showcase
The complete, unedited operation video tracking the entire lifecycle of the environment—starting from the hypervisor layer, passing through pfSense/MikroTik routing, up to the cellular communication links—is hosted securely via the link below:

🔗 [**Click Here to Watch the Full Verification Video on Streamable**](https://streamable.com/h73uz5)

* **00:00 - Boot & Hypervisor Layer:** Initial Proxmox VE node startup sequence (`pve-cesar`), initializing memory mappings and bringing up software-defined virtual bridges (`vmbr0` / `vmbr1`).
* **Micro-services & Network Appliances Initialization:** Core virtual routing and perimeter security startup inside **pfSense (CT 100)** and border management alignment via **MikroTik RouterOS / Winbox (CT 200)**.
* **5G SA Core & RAN Emulation:** Native systemd daemon verification inside **Open5GS Core (CT 103)** and successful **SCTP association (Port 36412)** setup with **UERANSIM / gNB (CT 106)**.
* **Live Traffic Routing & Telemetry:** Subscriber profile attach validation leading to active User Equipment (UE) successfully routing live internet traffic through the virtualized UPF data plane, monitored side-by-side on custom Zabbix (`10.0.0.163`) and Grafana (`10.0.0.164`) dashboards.

---

## ⚠️ PROPRIETARY NOTICE & SCIENTIFIC EMBARGO

> **[INTELLECTUAL PROPERTY PROTECTION]**
> The structural blueprints, detailed network topology maps, customized routing matrices, pfSense/MikroTik rule sets, deployment YAML files, and automation source codes associated with this laboratory are currently under a strict **Scientific Embargo**.  
> 
> This laboratory acts as the experimental foundation for an **original, autoral technical-scientific research paper** submitted for peer-review at a prestigious symposium. In compliance with academic originality and copyright policies, the underlying source codes and step-by-step deployment blueprints are hidden from public view and will be officially released under an open-source license **ONLY** after the official publication and homologation of the scientific paper.  
> 
> **© César Ueler | Lab Home Infrastructure - Todos os Direitos Reservados.**
