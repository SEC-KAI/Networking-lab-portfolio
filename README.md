# Cisco Networking & Infrastructure Lab Portfolio

This repository documents hands-on networking labs focused on **Cisco switching, routing, network services, redundancy, troubleshooting, and device hardening**.

Rather than keeping each school exercise as a separate project, I grouped related labs into larger technical categories that show how the concepts work together. Each project contains its own documentation and, where available, device configurations, verification output, supporting evidence, and Cisco Packet Tracer files.

## Core Skills Demonstrated

- **Layer 2 Switching:** VLANs, 802.1Q trunks, DTP, STP, EtherChannel, PortFast, BPDU Guard
- **Switch Security:** Port security, DHCP snooping, unused-port hardening, secure trunk configuration
- **Layer 3 Routing:** Inter-VLAN routing, IPv4/IPv6 static routing, default routes, host routes, floating static routes
- **Network Services:** DHCPv4, DHCP relay, management SVIs
- **High Availability:** HSRP, gateway failover, redundant Layer 2 paths
- **Device Administration:** SSH, local authentication, RSA keys, password policies, login protection
- **Troubleshooting:** Routing-table analysis, interface validation, connectivity testing, failure recovery
- **Dual Stack:** IPv4 and IPv6 addressing, routing, and verification

---

## Projects

| Project | Focus | What It Demonstrates |
|---|---|---|
| **[01 - Secure Switching](./01-secure-switching)** | Layer 2 security | Port security, DHCP snooping, static trunks, DTP hardening, black-hole VLANs, PortFast, and BPDU Guard |
| **[02 - VLAN Segmentation & Inter-VLAN Routing](./02-vlan-segmentation-and-inter-vlan-routing)** | Segmentation and Layer 3 connectivity | VLAN design, access ports, management SVIs, voice VLANs, trunking, native VLAN troubleshooting, and router-on-a-stick |
| **[03 - Layer 2 Resiliency](./03-layer2-resiliency)** | STP and EtherChannel | Root-bridge analysis, blocked-path behavior, STP convergence, PAgP, LACP, and port-channel validation |
| **[04 - Dual-Stack Static Routing & Troubleshooting](./04-dual-stack-static-routing-and-troubleshooting)** | IPv4/IPv6 routing | Static/default/host routes, floating backup routes, administrative distance, route-table analysis, and systematic troubleshooting |
| **[05 - DHCP & First-Hop Redundancy](./05-dhcp-and-first-hop-redundancy)** | Network services and availability | Centralized DHCPv4 with relay and HSRP gateway redundancy with active/standby failover testing |
| **[06 - Network Foundations & Device Hardening](./06-network-foundations-and-device-hardening)** | Infrastructure fundamentals | IPv4/IPv6 addressing, switch management, router configuration, SSH administration, authentication, and baseline IOS hardening |

---

## What These Labs Show

### Secure and Segmented Switching

I configured VLAN-based segmentation and hardened access-layer switching by controlling which devices can connect, restricting trunk behavior, protecting DHCP operation, and preventing endpoint-facing ports from influencing spanning-tree topology.

### Resilient Layer 2 Networks

I worked with redundant switching paths using **STP** and **EtherChannel**, including observing convergence after a link failure and validating negotiated link aggregation with both **PAgP** and **LACP**.

### Routing and Dual-Stack Connectivity

The routing projects cover **IPv4 and IPv6** from basic gateway configuration through router-on-a-stick and multi-router static routing. I also configured floating static routes and used administrative distance to provide backup paths.

### Network Services and High Availability

I configured centralized **DHCPv4** across routed networks using `ip helper-address` and tested **HSRP** to provide a virtual default gateway that survives a router or link failure.

### Device Hardening and Administration

I configured Cisco IOS devices for secure remote management using **SSH**, local authentication, RSA keys, encrypted credentials, minimum password requirements, idle timeouts, and login blocking.

### Troubleshooting and Verification

The projects are documented around verification rather than configuration alone. I used commands such as:

```text
show vlan brief
show interfaces trunk
show spanning-tree
show etherchannel summary
show port-security
show ip dhcp snooping
show ip dhcp binding
show standby
show ip route
show ipv6 route
show ip interface brief
show ipv6 interface brief
ping
traceroute
```

I used these outputs to confirm expected behavior, isolate configuration problems, and validate recovery after failures.

---

## Repository Structure

```text
Networking-lab-portfolio/
│
├── 01-secure-switching/
├── 02-vlan-segmentation-and-inter-vlan-routing/
├── 03-layer2-resiliency/
├── 04-dual-stack-static-routing-and-troubleshooting/
├── 05-dhcp-and-first-hop-redundancy/
├── 06-network-foundations-and-device-hardening/
└── README.md
```

Individual project folders may contain:

```text
README.md        Project explanation and technical reasoning
configs/         Device configuration and command output
evidence/        Verification evidence and supporting artifacts
packet-tracer/   Cisco Packet Tracer lab files
```

---

## How I Approach the Labs

My goal with these projects is not only to make the topology work, but to understand **why the configuration works and how to prove it**.

My general workflow is:

```text
Understand the requirement
        ↓
Build and configure the topology
        ↓
Verify interfaces, VLANs, routes, and protocols
        ↓
Test end-to-end connectivity
        ↓
Introduce or identify failure conditions
        ↓
Troubleshoot using device state and command output
        ↓
Document the result
```

This repository is an ongoing record of my practical networking work as I continue developing skills in **network engineering, infrastructure, and cybersecurity**.
