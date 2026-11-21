# Projects

A mix of infrastructure, mobile, and data projects — spanning the full stack from bare metal to UI.

[← back to README](READMEv2.md)

---

## [SOC-in-a-Box](https://github.com/RocketSurgeon226/Dirty-SOC-s-SOC-in-aBox)

*Capstone · Python · Fall 2026*

A low-cost (~$188) Raspberry Pi 5 home network security system built by a 5-person team. The Pi passively watches traffic through a managed switch's mirrored (SPAN) port, Suricata flags suspicious activity, and a Python service turns each detection into a plain-language alert card a homeowner can act on: what happened, how serious it is, which device, and one next step. It covers six categories: known-malicious IP/domain contact, plaintext credentials, port scans, new devices, unusual outbound volume, and excessive ad/tracker DNS.

I lead the team and own packet capture and sensor setup: building Suricata from source on the Pi, configuring SPAN mirroring so the network stays up even if the Pi goes down, loading the ET Open and URLhaus rulesets, and writing the port-scan and plaintext-credential detection rules.

**Tech:** `Raspberry Pi 5` `Suricata` `ET Open` `URLhaus` `Python` `Flask/FastAPI` `pytest` `GitHub Actions`

---

## [Home Lab](HOMELAB.md)

Self-hosted infrastructure on Proxmox VE: media serving, DNS filtering, VPN, and a segmented VLAN network behind an OPNsense firewall.

**Stack:** Proxmox · OPNsense · Omada SDN · Docker · Cloudflare Tunnel

---

## [Cr8r Soul](https://github.com/RocketSurgeon226/Cr8r-Soul--Final-Project---iOS-App--SwiftUI--INFOTC-4405)
*SwiftUI · Final project, INFOTC 4405 · May 2026*

A SwiftUI app for tracking a physical and digital music collection: vinyl, cassette, CD, MiniDisc, 8-Track, shellac and digital. Owned records live in your **Cr8**, wanted ones in your **Cr8 Shipment**, each with a 1–5 rating, liner notes, and one or more elemental tags: Water/Strings, Earth/Percussion, Fire/Brass, Air/Woodwinds. Includes a "Dig Mode" randomizer for rediscovering old finds and a Swift Charts "Soul Stats" dashboard. All data stays on the device with CoreData.

One of the harder bugs was a stack-overflow crash in the dashboard, traced to a view model recomputing on every state change — fixed by converting `DashboardViewModel` to a push-based pattern with a single `recompute()` entry point.

**Tech:** `Swift` `SwiftUI` `Swift Charts` `CoreData`

---

## SalesDataAnalyzer
*C# / .NET*

A C#/.NET console application that ingests supermarket sales CSV data and processes it with LINQ to surface trends — built and iterated on in VS Code.

**Tech:** `C#` `.NET` `LINQ` `CSV processing`

---

[← back to README](READMEv2.md)
