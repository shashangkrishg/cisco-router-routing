# 🌐 Cisco Packet Tracer — Two-Network Router Configuration

<p align="center">

![Cisco](https://img.shields.io/badge/Cisco-Packet%20Tracer-1BA0D7?style=for-the-badge\&logo=cisco\&logoColor=white)
![Networking](https://img.shields.io/badge/Networking-IPv4-blue?style=for-the-badge)
![Routing](https://img.shields.io/badge/Routing-Static%20%26%20Connected-green?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)

</p>

<p align="center">
  <b>A hands-on Cisco Packet Tracer lab demonstrating IPv4 addressing, router interface configuration, routing, and end-to-end connectivity between two separate networks.</b>
</p>

---

## 📌 Project Overview

This project demonstrates how a **Cisco router connects two separate IPv4 networks** using Cisco Packet Tracer.

The lab was built from scratch to practice fundamental networking concepts including:

* IPv4 addressing
* Subnetting
* Default gateways
* Router interface configuration
* Connected routes
* Network troubleshooting
* End-to-end connectivity testing

---

## 🗺️ Network Topology

```text
                         CISCO ROUTER
                    ┌────────────────────┐
                    │                    │
             Fa0/0  │                    │  Fa1/0
                    │                    │
                    └───────┬─────┬──────┘
                            │     │
                           SW1   SW2
                            │     │
                           PC1   PC2
```

### Network Layout

```text
192.168.10.0/24                         192.168.20.0/24

PC1                                      PC2
│                                        │
│ 192.168.10.10                          │ 192.168.20.10
│                                        │
SW1                                      SW2
│                                        │
│                                        │
└──── Fa0/0 ── ROUTER ── Fa1/0 ────────┘
              │          │
        192.168.10.1  192.168.20.1
```

---

## 📊 IP Addressing Table

| Device | Interface       | IP Address      | Subnet Mask     | Default Gateway |
| ------ | --------------- | --------------- | --------------- | --------------- |
| PC1    | FastEthernet0   | `192.168.10.10` | `255.255.255.0` | `192.168.10.1`  |
| Router | FastEthernet0/0 | `192.168.10.1`  | `255.255.255.0` | —               |
| Router | FastEthernet1/0 | `192.168.20.1`  | `255.255.255.0` | —               |
| PC2    | FastEthernet0   | `192.168.20.10` | `255.255.255.0` | `192.168.20.1`  |

---

## 🔧 Technologies & Concepts

<p align="center">

![Cisco IOS](https://img.shields.io/badge/Cisco%20IOS-Configuration-1BA0D7?style=flat-square\&logo=cisco\&logoColor=white)
![IPv4](https://img.shields.io/badge/IPv4-Addressing-blue?style=flat-square)
![Subnetting](https://img.shields.io/badge/Subnetting-%2F24-orange?style=flat-square)
![Routing](https://img.shields.io/badge/Routing-Connected%20Routes-green?style=flat-square)
![CLI](https://img.shields.io/badge/CLI-Cisco%20IOS-black?style=flat-square)

</p>

---

## ⚙️ Router Configuration

The router was configured with two FastEthernet interfaces.

### Interface 1

```text
interface FastEthernet0/0
ip address 192.168.10.1 255.255.255.0
no shutdown
```

### Interface 2

```text
interface FastEthernet1/0
ip address 192.168.20.1 255.255.255.0
no shutdown
```

---

## 🔍 Verification & Testing

### 1. Interface Verification

```text
show ip interface brief
```

Used to verify that the router interfaces were correctly configured and operational.

Expected result:

```text
FastEthernet0/0    192.168.10.1    up    up
FastEthernet1/0    192.168.20.1    up    up
```

### 2. Routing Table

```text
show ip route
```

The router automatically learned both networks as **directly connected routes**.

```text
C    192.168.10.0/24
C    192.168.20.0/24
```

### 3. End-to-End Connectivity

From PC1:

```text
ping 192.168.20.10
```

A successful response confirmed connectivity between the two different networks.

---

## 🧠 What I Learned

Through this lab, I learned how to:

* Configure Cisco router interfaces
* Assign IPv4 addresses
* Understand `/24` subnetting
* Configure default gateways
* Enable interfaces using `no shutdown`
* Read `show ip interface brief`
* Read a Cisco routing table
* Understand directly connected routes
* Troubleshoot physical connectivity
* Verify network connectivity using `ping`
* Understand how routers forward traffic between different networks

---

## 🛠️ Troubleshooting

During the lab, an interface initially showed a **down** state.

The issue was traced to the **physical cable connection** between the router and switch.

After correcting the connection and enabling the interface with:

```text
no shutdown
```

the interface became operational.

This demonstrated an important real-world troubleshooting principle:

> **Always check the physical layer before assuming the configuration is wrong.**

---

## 📁 Project Structure

```text
cisco-day-03-router-routing/
│
├── 📄 README.md
├── 📄 day3-router-routing.pkt
├── 📄 router-config.txt
├── 🖼️ topology.png
│
└── 📁 screenshots/
    ├── interfaces.png
    ├── routing-table.png
    └── successful-ping.png
```

---

## 🎯 Project Objective

The primary objective was to build and configure a small routed network from scratch and demonstrate successful communication between two different IPv4 networks.

### Result

**✅ Successfully completed**

PC1:

```text
192.168.10.10
```

was able to communicate with PC2:

```text
192.168.20.10
```

through the Cisco router.

---

## 📚 Skills Demonstrated

<p align="center">

![Networking](https://img.shields.io/badge/Computer%20Networking-Intermediate-blue?style=for-the-badge)
![IPv4](https://img.shields.io/badge/IPv4-Addressing-blue?style=for-the-badge)
![Cisco](https://img.shields.io/badge/Cisco-IOS-1BA0D7?style=for-the-badge\&logo=cisco\&logoColor=white)
![Troubleshooting](https://img.shields.io/badge/Network-Troubleshooting-orange?style=for-the-badge)
![Packet Tracer](https://img.shields.io/badge/Packet%20Tracer-Lab-green?style=for-the-badge)

</p>

---

## 🚀 Next Steps

This project is part of my **30-Day Junior Network Engineer Portfolio**.

Upcoming labs will progressively cover:

* DHCP
* VLANs
* Trunking
* Inter-VLAN Routing
* Static Routing
* OSPF
* Network Troubleshooting
* Enterprise Network Design

---

### 👨‍💻 Author

**Junior Network Engineering Portfolio**

> Building practical networking skills through hands-on labs and progressively complex Cisco Packet Tracer projects.
