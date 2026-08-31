# Projects

A mix of infrastructure, mobile, and data projects — spanning the full stack from bare metal to UI.

[← back to README](READMEv2.md)

---

## [Home Lab](HOMELAB.md)

Self-hosted infrastructure on Proxmox VE: media serving, DNS filtering, VPN, and a segmented VLAN network behind an OPNsense firewall.

**Stack:** Proxmox · OPNsense · Omada SDN · Docker · Cloudflare Tunnel

→ full write-up: [HOMELAB.md](HOMELAB.md)

---

## [Cr8r Soul](https://github.com/RocketSurgeon226/Cr8r-Soul--Final-Project---iOS-App--SwiftUI--INFOTC-4405)
*SwiftUI · May 2026*

A music collection tracker app built in SwiftUI. Started on CoreData, then migrated to JSON-based persistence to work around Swift Playgrounds limitations. Organizes a collection around an elemental tagging system — Water/Strings, Earth/Percussion, Fire/Brass, Air/Woodwinds — plus a "Dig Mode" randomizer for rediscovering old finds and a Swift Charts dashboard for visualizing the collection.

One of the harder bugs was a stack-overflow crash in the dashboard, traced to a view model recomputing on every state change — fixed by converting `DashboardViewModel` to a push-based pattern with a single `recompute()` entry point.

**Tech:** `Swift` `SwiftUI` `JSON persistence` `Swift Charts`

---

## SalesDataAnalyzer
*C# / .NET*

A C#/.NET console application that ingests supermarket sales CSV data and processes it with LINQ to surface trends — built and iterated on in VS Code.

**Tech:** `C#` `.NET` `LINQ` `CSV processing`

---

[← back to README](READMEv2.md)
