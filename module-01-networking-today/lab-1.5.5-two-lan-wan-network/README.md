# Lab 1.5.5 – Two-LAN WAN Network

## Overview

This lab demonstrates the design and configuration of a simple network consisting of two LANs connected through a WAN. The network was built in Cisco Packet Tracer using PCs, switches, and routers.

The implementation includes IPv4 addressing, router interface configuration, default gateways, static routing, and connectivity verification between devices on different networks.

## Objectives

- Build two separate LANs connected through a WAN.
- Configure IPv4 addresses and subnet masks on network devices.
- Configure default gateways on end devices.
- Configure router interfaces for LAN and WAN connectivity.
- Configure static routes between the two LANs.
- Verify local and end-to-end connectivity using `ping`.

## Network Topology

The network consists of two separate LANs connected through a point-to-point WAN link between two routers.

- **LAN 1:** PC1 and PC2 connect to Switch S1, which connects to Router R1.
- **WAN:** Router R1 connects directly to Router R2.
- **LAN 2:** Router R2 connects to Switch S2, which connects to PC3 and PC4.

### Network Structure

PC1 ─┐                                      ┌─ PC3
     ├─ S1 ── R1 ───── WAN ───── R2 ── S2 ─┤
PC2 ─┘                                      └─ PC4

192.168.1.0/24     10.0.0.0/30     192.168.2.0/24
     LAN 1              WAN              LAN 2

### Devices Used

| Device | Model | Purpose |
|---|---|---|
| R1 | Cisco 2911 Router | Routes traffic between LAN 1 and the WAN |
| R2 | Cisco 2911 Router | Routes traffic between the WAN and LAN 2 |
| S1 | Cisco 2960-24TT Switch | Connects devices within LAN 1 |
| S2 | Cisco 2960-24TT Switch | Connects devices within LAN 2 |
| PC1–PC4 | PC-PT | End devices used for connectivity testing |
