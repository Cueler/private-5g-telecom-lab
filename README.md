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

The sections below contain verified, unedited screen captures of the environment in full production state, validating the architectural stability and throughput.

### 🖥️ Core 5G SA End-to-End Operation Showcase
The demonstration video showcases the complete lifecycle of the private network running smoothly:

* **00:00 - 00:04:** An active User Equipment (UE) successfully routing live data traffic (ICMP/Ping) to the public internet through the virtualized UPF data plane, achieving an average latency of **9.7ms** with **0% packet loss**.
* **00:08 - 00:18:** Real-time **SCTP association** and NGAP setup procedure confirmation between the emulated gNB and the AMF control plane.
* **00:27 - 00:36:** Micro-service footprint inspection via systemd, proving ultra-high resource efficiency (the core UPF engine requires only **26MB of RAM** under operational state).
* **00:41 - 00:46:** Dynamic subscriber profile validation via the centralized WebUI management panel, followed by host-level telemetry observation on custom Grafana dashboards (`pve-cesar`).

*(Insert video/gif reference here after upload)*

---

## ⚠️ PROPRIETARY NOTICE & SCIENTIFIC EMBARGO

> **[INTELLECTUAL PROPERTY PROTECTION]** > The structural blueprints, detailed network topology maps, customized routing matrices, pfSense/MikroTik rule sets, deployment YAML files, and automation source codes associated with this laboratory are currently under a strict **Scientific Embargo**.  
> 
> This laboratory acts as the experimental foundation for an **original, autoral technical-scientific research paper** submitted for peer-review at a prestigious symposium. In compliance with academic originality and copyright policies, the underlying source codes and step-by-step deployment blueprints are hidden from public view and will be officially released under an open-source license **ONLY** after the official publication and homologation of the scientific paper.  
> 
> **© César Ueler | Lab Home Infrastructure - Todos os Direitos Reservados.**
