# AdGuard Home — Network-Wide Ad Blocking

Deployed: October 7, 2026

## Overview
Self-hosted DNS filtering for my whole home network, running in an
LXC container on Proxmox VE (Dell OptiPlex).

## Setup
| Item | Value |
|---|---|
| Host | Proxmox VE 9.2 |
| Container | Debian 13 LXC, 1 core, 512 MB RAM, 4 GB disk |
| IP | Static 192.168.1.11 (DHCP reservation on router) |
| Upstream DNS | Cloudflare + Quad9 over DNS-over-HTTPS |
| Blocklists | AdGuard DNS filter, HaGeZi Normal |

## Testing
```bash
$ dig @192.168.1.11 doubleclick.net   # → 0.0.0.0 (blocked)
$ dig @192.168.1.11 google.com        # → real IPs (allowed)
```
## Lessons Learned
- Service names are case-sensitive (`AdGuardHome`, not `adguardhome`)
- AdGuard's brute-force protection locked me out after failed logins (HTTP 429)
- Leaving the router's secondary DNS blank let it insert itself, which leaked DNS around AdGuard
-<img width="1142" height="1299" alt="Screenshot 2026-10-08 032020" src="https://github.com/user-attachments/assets/5a7c69ae-c68a-4a1f-be95-a3d3be28483a" />
- <img width="955" height="885" alt="Screenshot 2026-10-08 032118" src="https://github.com/user-attachments/assets/cfe6827c-cbcd-4bba-bb62-7fad4ae89759" />
<img width="2552" height="1076" alt="Screenshot 2026-10-08 032740" src="https://github.com/user-attachments/assets/ba92abf9-8ba3-454f-b1e9-dc9a46c4a075" />
<img width="1900" height="707" alt="Screenshot 2026-10-08 032941" src="https://github.com/user-attachments/assets/3412b147-73e2-4b19-bf02-cdef6b52402d" />
