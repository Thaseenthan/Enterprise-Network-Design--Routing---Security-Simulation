# Enterprise Network Design, Routing & Security Simulation

A multi-site enterprise network designed and simulated using **Cisco Packet Tracer**.  
The project demonstrates practical networking concepts including VLAN segmentation, inter-VLAN routing, DHCP, DNS, NAT/PAT, static routing, OSPF, ACL-based security, and network troubleshooting.

---

## Project Overview

This project simulates a company's **Main Office and Branch Office** connected through routers, with separate networks for Administration, Engineering, Servers, and Branch users.

The network was designed to provide:

- Network segmentation using VLANs
- Inter-VLAN communication
- Automatic IP address assignment using DHCP
- Internal DNS and HTTP services
- Internet connectivity using NAT/PAT
- Static routing and dynamic routing using OSPF
- Branch network connectivity
- Access control using extended ACLs
- Network troubleshooting and connectivity verification

---

## Network Topology

The network consists of:

- **R1** – Main Office Router
- **R2** – Branch Office Router
- **ISP Router** – Simulated Internet Service Provider
- **Main Office Switch**
- **Branch Office Switch**
- **PC-Admin**
- **PC-Engineering**
- **DNS/Web Server**
- **PC-Branch**
- **Internet Server**

## Project Overview
1. Install Cisco Packet Tracer.
2. Download or clone this repository.
3. Open:
Enterprise-Network-Design.pkt
4. Review the topology and device configurations.
5. Use Cisco IOS commands to verify routing, VLANs, OSPF, ACLs, DHCP, and NAT.
6. Perform the connectivity tests between the different networks.   

### Network Structure

```text
                         ┌─────────────────┐
                         │  Internet Server│
                         │    8.8.8.8      │
                         └────────┬────────┘
                                  │
                            ┌─────┴─────┐
                            │    ISP    │
                            │  Router   │
                            └─────┬─────┘
                                  │
                           203.0.113.0/30
                                  │
                            ┌─────┴─────┐
                            │    R1     │
                            │Main Office│
                            └──┬────┬───┘
                               │    │
                     VLANs     │    │ 10.0.0.0/30
                               │    │
                ┌──────────────┘    └──────────────┐
                │                                  │
        ┌───────┴────────┐                   ┌─────┴─────┐
        │ Main Office    │                   │    R2     │
        │    Switch      │                   │  Branch   │
        └─┬────┬────┬────┘                   └─────┬─────┘
          │    │    │                              │
          │    │    │                              │
       VLAN10 VLAN20 VLAN30                  192.168.40.0/24
          │    │    │                              │
          │    │    │                       ┌──────┴──────┐
          │    │    │                       │   Branch    │
          │    │    │                       │   Switch    │
          │    │    │                       └──────┬──────┘
          │    │    │                              │
       Admin  Eng  Server                       PC-Branch

       
   