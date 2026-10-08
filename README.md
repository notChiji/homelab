# 🖥️ homelab

My self-hosted home lab, built to learn networking, Linux, and security hands-on.

## Hardware
| Device | Role |
|---|---|
| Dell OptiPlex (Intel 7th gen) | Proxmox VE 9.2 hypervisor |
| TP-Link AX3000 | Router, DHCP, address reservations |

## Network Plan
| Range | Purpose |
|---|---|
| 192.168.1.1 | Router |
| 192.168.1.2 – .50 | Static zone (servers) |
| 192.168.1.51 – .253 | DHCP (client devices) |

## Services
| Service | IP | Status | Docs |
|---|---|---|---|
| Proxmox VE | 192.168.1.10 | ✅ Live | — |
| AdGuard Home | 192.168.1.11 | ✅ Live | [adguard-home](./adguard-home) |
| Grafana + Prometheus | — | 🔜 Planned | — |
| Wazuh | — | 🔜 Planned | — |
