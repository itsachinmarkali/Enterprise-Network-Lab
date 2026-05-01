# 🏢 Enterprise Network Simulation (Lab 3)

## 📌 Overview

This project demonstrates a **real-world enterprise network design** built using Cisco Packet Tracer.

It includes VLAN segmentation, inter-VLAN routing using a Layer 3 switch, DHCP configuration, ACL-based security, port security, and wireless network integration.

---

## 🧠 Network Design

The network is divided into multiple departments using VLANs:

* **HR Department** → VLAN 10
* **IT Department** → VLAN 20
* **Finance Department** → VLAN 30
* **Wireless Users (WiFi)** → VLAN 40

---

## 🌐 IP Addressing Scheme

| VLAN | Department | Network         | Gateway      |
| ---- | ---------- | --------------- | ------------ |
| 10   | HR         | 192.168.10.0/24 | 192.168.10.1 |
| 20   | IT         | 192.168.20.0/24 | 192.168.20.1 |
| 30   | Finance    | 192.168.30.0/24 | 192.168.30.1 |
| 40   | WiFi       | 192.168.40.0/24 | 192.168.40.1 |

---

## ⚙️ Features Implemented

### ✅ VLAN Segmentation

* Created separate broadcast domains for each department

### ✅ Inter-VLAN Routing

* Enabled using SVI (Switch Virtual Interfaces) on Layer 3 switch

### ✅ DHCP Server

* Automatic IP address assignment for all VLANs

### ✅ ACL Security

* Restricted access between departments
* HR network is blocked from accessing Finance network

### ✅ Port Security

* Prevents unauthorized devices from connecting to access ports

### ✅ Wireless Integration

* WiFi users connected via Access Point mapped to VLAN 40

### ✅ STP Optimization

* Core switch configured as root bridge for efficient traffic flow

---

## 🔒 Access Control List (ACL)

```bash
deny ip 192.168.10.0 0.0.0.255 192.168.30.0 0.0.0.255
permit ip any any
```

**Explanation:**

* Blocks traffic from HR (VLAN 10) to Finance (VLAN 30)
* Allows all other traffic

---

## 🧪 Testing & Verification

| Test Case                  | Result                  |
| -------------------------- | ----------------------- |
| HR → IT Communication      | ✅ Success               |
| HR → Finance Communication | ❌ Blocked (ACL Working) |
| IT → Finance Communication | ✅ Success               |
| WiFi Connectivity          | ✅ Working               |
| DHCP IP Assignment         | ✅ Working               |
| Port Security              | ✅ Working               |

---

### 🔹 Network Topology

![Topology](screenshots/topology.png)

---

## 🏗️ Topology Description

* Core Layer 3 Switch handles routing and DHCP
* Access Switch connects end devices
* Trunk link carries multiple VLANs
* Wireless AP connects WiFi users to VLAN 40

---

## 🎯 Learning Outcomes

* Understanding VLAN segmentation
* Configuring inter-VLAN routing
* Implementing DHCP services
* Applying ACL for network security
* Configuring port security
* Integrating wireless networks
* Designing enterprise-level topology

---

## 💼 Use Case

This project simulates a real enterprise network where:

* Departments are isolated for security
* Controlled communication is enforced
* Wireless users are integrated securely
* Network is scalable and manageable

---

## 👨‍💻 Author

**SACHIN MARKALI**

---

## ⭐ Notes

* Built for learning and demonstration purposes
* Can be extended with OSPF, NAT, and Internet simulation
* Useful for networking interviews and practical understanding

---
