
# 🌐 Chapter 1: Hypervisor Isolation & Layer-2/Layer-3 Boundary Routing

This deployment stage validates the underlying virtualization fabric and the hardware-abstracted routing constraints that ensure complete cryptographic and packet isolation for the private 5G core network.

---

## 🎛️ Section 1.1: MikroTik RouterOS Core Border Gateway (CT 200)
* **Operational Role:** Boundary Layer-3 Routing, NAT Translation, and Traffic Shaping.
* **Architecture Essence:** This segment acts as the automated upstream provider handler. It manages external packet network delivery, routes administrative traffic, and acts as the entry-point shield, ensuring that internal high-frequency core network frames are structurally separated from host local area loops.
* **Subsystem Live Session Proof:** 🔗 [**Watch MikroTik RouterOS & Winbox Session Verification**](COLE_AQUI_O_LINK_DO_STREAMABLE_DO_VIDEO_MIKROTIK)

---

## 🌉 Section 1.2: Host Software-Defined Bridge Network Interconnection (CT 104)
* **Operational Role:** Layer-2 Virtual Bridge Interconnection (`vmbr1` ↔ `vmbr0`).
* **Architecture Essence:** A dedicated, ultra-low latency bridging container engineered to act as a strict network leg ("perna entre dois mundos"). It binds virtual machine interfaces together under structural control, mapping isolated subnets securely so that traffic can flow from the edge routing blocks down to the inner core cellular nodes without leaking packet headers.
* **Subsystem Live Session Proof:** 🔗 [**Watch Host Bridge Interface Initialization Video**](COLE_AQUI_O_LINK_DO_STREAMABLE_DO_VIDEO_DA_PERNA)
