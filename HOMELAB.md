# Home Lab — A network I own end to end

[← back to README](README.md)

A single Beelink mini PC running Proxmox VE grew into a full home network: media serving, DNS filtering, a WireGuard VPN mesh, a segmented VLAN topology behind an OPNsense firewall, and a TP-Link Omada SDN stack — with everything documented as it was built, broken, and fixed.

**Full technical write-up:** [`roadmap.html`](roadmap.html) · **Interactive topology map:** [`topology.html`](topology.html)

---

## Stack

**Hardware**

| | |
|---|---|
| Host | Beelink Mini S12 — N95, 16GB RAM, 500GB SSD |
| Storage | 2× 1.8TB HDD via SABRENT USB dock |
| Network gear | TP-Link Omada — ER605 router, 8-port switch, EAP225 AP |

**Software (OS, LXCs, and VMs)**

| | |
|---|---|
| Hypervisor | Proxmox VE (LXC + VM) |
| Firewall / router | OPNsense |
| Containers | Docker + Portainer |
| Media | Jellyfin, Immich |
| Network | AdGuard Home, Tailscale, Omada SDN Controller |
| Exposure | Cloudflare Tunnel → jerms226.net,  Nginx Proxy Manager (NPM) |
| Monitoring | Uptime Kuma, Netdata |
| Backup | Proxmox Backup Server (PBS) |

---

## Topology (simplified)

```
PVE host (192.168.1.150)
├── Jellyfin                                                               CT100 · .151
├── Docker / Portainer                                                     CT101 · .152
  ├── Immich, Cloudflare Tunnel, Nginx Proxy Manager, Uptime Kuma, Netdata
├── Tailscale subnet router                                                CT102 · .153
├── Proxmox Backup Server                                                  VM103 · .154
├── OPNsense (firewall/router)                                             VM104 · .1
├── AdGuard Home (DNS)                                                     CT105 · .156
└── Omada SDN Controller                                                   CT106 · .157
  ├── ER605 router, 8-port switch, EAP225 AP 
```

→ full topology map: [`topology.html`](topology.html)

---

## Troubleshooting Instances

**VLAN segmentation — bridge silently dropped VLAN tags**
Per-container tags were being ignored because `vmbr0` was never set VLAN-aware. Root-caused via `bridge vlan show`, fixed in `/etc/network/interfaces`.

**Omada adoption — router stuck "Disconnected" for days**
Traced through a double-NAT chain to a UDP inform probe hitting the wrong port and a firewall rule silently dropping WAN traffic — fixed with targeted OPNsense pass rules and the Omada Discovery Utility.

**Container networking — two "adopt failed" outages, one root cause**
A container's veth interface and a VM's tap interface had both silently detached from their bridge after reboot — invisible in the UI, only visible via `ip link`.

**DNS routing — network-wide ad-filtering without touching devices**
Pushed AdGuard as the DHCP-assigned DNS server via OPNsense, plus a NAT redirect to catch hardcoded-DNS devices like smart TVs.

---

[← back to README](READMEv2.md)
