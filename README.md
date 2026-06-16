# DMZ_ZONE_NETWORK_LAB
Cisco Packet Tracer lab simulating a multi-zone enterprise network with DMZ, OSPF, static routing, NAT/PAT, ACLs, and BGP

## Overview
This lab demonstrates a real-world enterprise network architecture divided into four security zones. It was built to practice network segmentation, routing design, NAT configuration, and layered access control.

## Network Zones
| Zone | Network | Description |
|------|---------|-------------|
| Internal LAN | 192.168.1.0/24 | Corporate workstations and internal server |
| DMZ | 172.16.1.0/24 | Publicly accessible web servers |
| Edge | 2.2.2.0/28 | DMZ router to ISP handoff |
| Internet (simulated) | 100.100.100.0/24 | External clients and remote user |

## Technologies Used
- **OSPF Area 0** — dynamic routing within the Internal LAN
- **Static Routing** — controlled routing in the DMZ (security by design)
- **NAT/PAT with Port Forwarding** — maps public IP 2.2.2.2 to internal DMZ servers
- **Access Control Lists (ACLs)** — restrict traffic between zones
- **BGP (AS100 / AS200)** — simulates ISP peering at the edge

## Key Design Decisions
- Static routes are used in the DMZ instead of OSPF to prevent internal topology from being advertised outward
- DMZ-SERVER2 uses alternate ports (8080/4443) because a public IP:port can only be forwarded once
- ACLs are sequenced to permit OSPF hellos before deny rules to preserve neighbor adjacency

## Files
| File | Description |
|------|-------------|
| `DMZ Zone.pkt` | Cisco Packet Tracer topology file |
| `DMZ_Zone_Project_Documentation.docx` | Full technical documentation |

## Author
**Franck Kashindi**  
CompTIA A+ | CompTIA Network+
