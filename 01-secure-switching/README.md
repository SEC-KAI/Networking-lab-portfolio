# Secure Switching

## Problem

An access-layer switch can provide connectivity while still exposing the network to unauthorized devices, rogue DHCP servers, accidental switching loops, and trunk negotiation risks. This project applies layered controls to two access switches in a routed VLAN environment.

## What I configured

- Converted inter-switch links to static 802.1Q trunks and disabled DTP negotiation.
- Assigned VLAN 100 as a dedicated native VLAN.
- Placed unused SW-1 ports in VLAN 999 (`BlackHole`) and administratively shut them down.
- Enabled port security on active SW-1 access ports.
- Limited learned MAC addresses to four per active port.
- Used a static secure MAC address for one endpoint and sticky learning on the remaining active access ports.
- Selected the `restrict` violation behavior so unauthorized frames are dropped and logged without shutting down the interface.
- Trusted only trunk-facing DHCP-snooping ports and rate-limited untrusted ports to five DHCP packets per second.
- Enabled DHCP snooping for VLANs 10, 20, and 99.
- Enabled PortFast and BPDU Guard on edge ports.

## Security reasoning

| Control | Risk reduced |
| --- | --- |
| Static trunk + DTP disabled | Unwanted trunk formation |
| Unused-port shutdown + black-hole VLAN | Unauthorized physical access |
| Port security | Unexpected endpoints and MAC flooding |
| DHCP snooping | Rogue DHCP responses and address manipulation |
| BPDU Guard | An endpoint introducing superior BPDUs |
| PortFast | Unnecessary convergence delay for end hosts |

The controls are complementary: port security restricts endpoint identities, DHCP snooping protects address assignment, and BPDU Guard protects the spanning-tree control plane.

## Verification

```text
show interfaces trunk
show port-security
show port-security interface <interface>
show ip dhcp snooping
show interfaces status
show spanning-tree summary
```

Expected results include static trunks with the intended native VLAN, secured access ports, trusted uplinks, DHCP rate limits on untrusted ports, and PortFast/BPDU Guard on edge interfaces.

## Skills demonstrated

Cisco switch hardening, Layer 2 threat awareness, secure trunk configuration, access-port control, and verification-driven implementation.

## Lab coverage

- Switch Security Configuration

See [evidence/README.md](evidence/README.md) for the exact supporting files to add.

