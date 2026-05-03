
# Enterprise Multi-Site Network — Cisco Packet Tracer

A multi-router enterprise network designed and configured in Cisco Packet Tracer 
for the *Networking Foundations* unit at AIT.

## 🎯 Project Overview

Designed and tested a 5-router enterprise topology supporting **10 LANs** across 
admin, operations, customer and engineering departments — with full end-to-end 
connectivity, dynamic addressing, and internal web services.

## 🏗️ Architecture

- **5 Routers:** Core, Admin, Ops, West, East
- **10 LANs:** Finance, Procurement, Sales, IT, HR, Executive, Engineering, R&D, CustomerA, CustomerB
- **WAN Links:** FastEthernet (Admin↔Core, Ops↔Core) and Serial (Core↔West, Core↔East, West↔East)

![Network Topology](topology-screenshot.png)

## 🔧 Technologies & Concepts

| Area | Implementation |
|---|---|
| Subnetting | VLSM on `10.20.5.0` block across networks of 4–28 hosts |
| Routing (Inner) | RIP on Admin, Core, Ops |
| Routing (Outer) | OSPF on Core, West, East |
| Redistribution | Core router redistributes routes between RIP and OSPF |
| Dynamic Addressing | DHCP server on West router for CustomerA & CustomerB networks |
| Services | Internal DNS server + Web server on the IT network |

## 📚 What I Learned

- VLSM design for efficient IP allocation across networks of varying sizes
- Configuring and troubleshooting two routing protocols (RIP, OSPF) in the same topology
- Route redistribution between dissimilar protocols
- DHCP pool configuration with exclusions and gateway settings
- DNS resolution and basic web hosting in a closed network

## 📂 Files

- `enterprise-network.pkt` — full Packet Tracer simulation
- `docs/` — topology diagram, subnetting and addressing tables
- `configs/` — running-config exports from each router

  ## 📄 Project Documentation

Detailed planning and design documentation submitted as part of the assignment:

- 📊 [Subnetting Table (VLSM)](subnetting-table.pdf) — full VLSM subnet allocation across all 10 LANs, with network/broadcast addresses, usable IP ranges and subnet masks
- 🗺️ [Addressing Table](addressing-table.pdf) — IP, subnet mask and default gateway assignments per device and interface

## 🚀 How to Open

1. Install [Cisco Packet Tracer](https://www.netacad.com/courses/packet-tracer) (free)
2. Open `enterprise-network.pkt`
3. Test connectivity with `ping` from any PC, or browse `www.siteXXXX.com` from a CustomerA/B host
