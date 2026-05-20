# 🧠 Chapter 4: 5G Standalone (SA) Core Network & RAN Emulation

This deployment stage validates the 3GPP Release 16 Standalone Core operational functions, control/user plane separation (CUPS), and Next-Generation Application Part (NGAP) signaling handshakes over secure SCTP transport.

---

## 🧠 Section 4.1: Open5GS Core Network Engine (CT 103)
* **Operational Role:** 5G Control & User Plane Orchestration (AMF, SMF, UPF, UDM, AUSF).
* **Architecture Essence:** Anchored at `10.0.0.170`, this Linux Container runs the decentralized core daemons. It manages subscriber cryptographic authentication keys, dynamically provisions PDU sessions, and binds the User Plane Function (UPF) data pipelines directly to the hypervisor routing layers.

### 🖥️ Subsystem Live Session Proofs:
* 🔗 [**Watch Open5GS Systemd Core Daemons Initialization**](https://streamable.com/ribyg7)  
  *Live terminal capture verifying active daemon execution logs. Validates clean initialization of the Access and Mobility Management Function (AMF) and Session Management Function (SMF) without protocol allocation errors.*
* 🔗 [**Watch Open5GS Web Administration Subscriber Provisioning**](https://streamable.com/b4vl7b)  
  *Walkthrough validating subscriber profiles registry, IMSI mappings, and slice allocation parameters inside the database front-end layer.*

---

## 📡 Section 4.2: UERANSIM Next-Gen Radio Access Network Emulation (CT 106)
* **Operational Role:** gNodeB (Base Station) Real-time Emulation & User Equipment (UE) Radio Bearer Attachment.
* **Architecture Essence:** Running at `10.0.0.171`, this appliance emulates the physical cellular Layer-2/Layer-3 stacks. It triggers the Stream Control Transmission Protocol (SCTP) handshake over Port 36412 to bind with the AMF core node.
* **Traffic Routing Matrix:** Upon successful authentication, it dynamically spawns localized virtual tunnel interfaces (`tun`), allowing emulated 5G handsets to establish end-to-end data session paths out to the internet through the pfSense secure gateway.

### 🖥️ Subsystem Live Session Proofs:
* 🔗 [**Watch UERANSIM Linux Container Micro-Service Startup**](https://streamable.com/rbzdif)  
  *Operational logging capturing the virtualization environment startup parameters for CT 106, allocating host dependencies and setting paths for cellular stack emulation.*
* 🔗 [**Watch gNodeB Connection & Active UE Handshake Session**](https://streamable.com/59jery)  
  *Technical validation capturing the precise moment of the radio link insertion. Shows the gNodeB pairing cleanly with the core, followed by the UE subscriber context registration and the immediate allocation of the tun interface for real traffic routing.*
