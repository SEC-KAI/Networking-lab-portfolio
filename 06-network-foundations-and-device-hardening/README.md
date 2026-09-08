# Network Foundations and Device Hardening

## Problem

A small routed network needed correct addressing, management access, and baseline device protection. The work progressed from a basic IPv4 topology to a dual-stack router configured for secure remote administration.

## What I built

### Small-network implementation

- Cabled one router, two access switches, and two end hosts.
- Addressed two `/24` LANs and configured router interfaces as their gateways.
- Configured switch management SVIs and default gateways.
- Applied hostnames, interface descriptions, encrypted privileged access, line authentication, and an MOTD banner.
- Saved the configurations and verified complete reachability.

### Dual-stack router and secure management

- Configured IPv4 and IPv6 addresses on two routed interfaces and a loopback.
- Enabled IPv6 unicast routing.
- Set a domain name, encrypted stored passwords, and enforced a 12-character password minimum.
- Created a local administrative account and generated RSA keys.
- Restricted VTY access to SSH and required local authentication.
- Applied console/VTY idle timeouts and temporary login blocking after repeated failures.
- Used SSH over IPv4 and IPv6 to inspect IOS, memory, interfaces, routes, and saved configuration.

## Security choices

SSH protects management traffic in transit; Telnet does not. Local VTY authentication, idle timeouts, login blocking, and encrypted secrets reduce exposure but do not replace centralized identity management in a production environment.

## Verification

```text
show ip interface brief
show ipv6 interface brief
show interfaces
show ip route
show ipv6 route
show version
show startup-config
show users
ping <ipv4-address>
ping <ipv6-address>
```

## Skills demonstrated

Physical/logical topology setup, IPv4/IPv6 addressing, management SVIs, gateways, loopbacks, secure IOS administration, configuration persistence, and command-line validation.

## Lab coverage

- Implement a Small Network
- Configure Basic Router Settings - Physical Mode

See [evidence/README.md](evidence/README.md) for supporting artifacts.

