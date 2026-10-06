[English](README.md) | [Русский](README_RU.md)

## Project status

The panel was entirely developed by AI from the author's description: no
code was written or reviewed by a human, and testing was superficial —
basic scenarios only. Check the security before using it in production
(at the very least, restrict access to the panel with a firewall).

I built this project for myself — to make managing VyOS easier.
To be honest, I don't run a fleet of routers; the panel simply
supports fleet management. I'm publishing it as is, with no plans
for active development. Fixes and improvements — as my own needs
arise. Forks are welcome: the project is a good foundation for
your own work.

**License: AGPLv3** — free to use, including commercially; all forks and
modifications must remain open under the same license (see the LICENSE
file).

**Download:** [Releases](https://github.com/noshka4/vyos_panel/releases/tag/2.4) — container image, install guide, tested VyOS ISO.

---

 **Note:** the panel UI and the install guide are in Russian only.
 No localization is planned. The panel's terminology follows VyOS CLI
 concepts, so it should still be usable if you know the CLI commands.

## VyOS Panel — deployed as a container on the router

A web panel for managing a fleet of VyOS routers. It installs directly
on one of the routers as a container (podman is built into VyOS) and
manages the other nodes via the standard HTTPS API. Tested on
`vyos-2026.10.01-0035-rolling`.

Version 2.4 is a full-featured GUI, not just monitoring: editing
interfaces and VLANs, firewall (rules and groups), NAT (masquerade/DNAT),
static routes and OSPF, DHCP/DNS/NTP, VPN (WireGuard, IPsec site-to-site,
GRE/IPIP/SIT/L2TPv3 tunnels, OpenVPN, L2TP/IPsec remote access), high
availability (VRRP, conntrack-sync, config-sync), services (syslog to
servers/SIEM, SNMP v2c/v3, LLDP, DDNS, DHCP relay, stunnel, PPPoE server
and client). Every change shows a preview of the `set`/`delete` commands
and is backed up automatically on the router, with one-click rollback.
Panel accounts: administrators and read-only observers, action log.
