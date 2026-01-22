
# Homelab — Virtualization & Testing

A documentation hub for my homelab focused on **virtualization and testing**.  
This repo contains notes, sanitized network references, and (ocasionally) topology images.

> **Privacy & Safety:** All hostnames and IP ranges here are **sanitized**.  
> Example subnet: `10.0.0.0/24` and placeholder FQDNs like `host01.lab.local`.

---

## Goals

- Learn and experiment with **virtualization**, **networking**, and **service deployment**  
- Maintain a reproducible, documented setup that’s easy to evolve  
- Share lessons learned and patterns that helped me

---

## Hardware Overview

| Role             | Model / Notes                        | Key Specs (if known)               |
|------------------|--------------------------------------|------------------------------------|
| Router           | TP-Link Omada **ER7206**             | WAN + VLANs, policy routing        |
| Core Switch      | Cisco **Catalyst 2960-48**           | 48 ports, managed L2               |
| Hypervisor Host  | Dell **PowerEdge <MODEL TBD>**       | Proxmox VE; CPU/RAM/Storage TBD    |
| Storage / NAS    | **TrueNAS**                          | ZFS; Snapshots; SMB/NFS/iSCSI      |
| DNS Server       | Small **NUC** (Linux)                | BIND (may change later)            |
| Power            | **UPS**                              | Graceful shutdowns, monitoring     |

<!-- TODO: Fill in Dell PowerEdge model, CPU, RAM, disk layout -->

---

## Virtualization & OS

- **Hypervisor:** Proxmox VE on the Dell PowerEdge  
- **VM OSes:** Ubuntu (for Linux VMs), Windows Server (for Windows VMs)  
- **Storage:** TrueNAS provides shared storage (ZFS)  
- **Backups:** <!-- TODO: Add backup strategy details (e.g., Proxmox backups to TrueNAS, snapshot cadence) -->

---

## Core Services

- **DNS:** BIND on Ubuntu running on the NUC  
  - Zone examples: `lab.local` (sanitized), reverse zone for `10.0.0.0/24`  
  - Future: Might switch DNS stack (evaluating Pi‑hole/AdGuard/unbound)

<!-- TODO: Add any additional services/containers if/when you deploy them -->
<!-- Examples to consider later:
- Reverse proxy (Traefik / NPM)
- Monitoring (Prometheus + Grafana, Telegraf)
- Syslog/Telemetry (Graylog/Loki)
- Media or Home Automation (Jellyfin/Home Assistant)
-->

---

## Repo Contents

This repository includes:

- `/notes/` — configuration notes, procedures, and troubleshooting
- `/topology/` — network diagrams (Mermaid &/or images)
- `/examples/` — sanitized sample configs (e.g., BIND snippets, VLAN examples)
