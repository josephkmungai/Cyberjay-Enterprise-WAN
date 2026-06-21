# IP Addressing Plan

## Project Information

**Project Name:** Cyberjay Enterprise WAN

**Author:** Joseph K. Mungai

**Program:** Diploma in Computer Network & System Administration / Cybersecurity

**Server Platform:** Windows Server 2019

---

# IP Addressing Strategy

Cyberjay Enterprise WAN uses the private IPv4 address block:

```text
10.0.0.0/8
```

The addressing scheme follows a hierarchical structure:

* Nairobi Headquarters → 10.10.x.x
* Mombasa Branch → 10.20.x.x
* Kisumu Branch → 10.30.x.x
* WAN Infrastructure → 10.40.x.x

Variable Length Subnet Masking (VLSM) is used while ensuring that no subnet is allocated fewer hosts than a /24 network.

---

# Nairobi Headquarters

## VLAN 10 - Administration & Finance

| Item              | Value         |
| ----------------- | ------------- |
| Network Address   | 10.10.10.0/24 |
| Subnet Mask       | 255.255.255.0 |
| Default Gateway   | 10.10.10.1    |
| Usable Hosts      | 254           |
| Broadcast Address | 10.10.10.255  |

### Devices

* Finance Staff
* Human Resource Staff
* Management Staff
* Administrative Printers

---

## VLAN 20 - Technical Operations

| Item              | Value         |
| ----------------- | ------------- |
| Network Address   | 10.10.20.0/23 |
| Subnet Mask       | 255.255.254.0 |
| Default Gateway   | 10.10.20.1    |
| Usable Hosts      | 510           |
| Broadcast Address | 10.10.21.255  |

### Devices

* Network Engineers
* System Administrators
* Cybersecurity Analysts
* Monitoring Systems

---

## VLAN 30 - Software Development

| Item              | Value         |
| ----------------- | ------------- |
| Network Address   | 10.10.30.0/23 |
| Subnet Mask       | 255.255.254.0 |
| Default Gateway   | 10.10.30.1    |
| Usable Hosts      | 510           |
| Broadcast Address | 10.10.31.255  |

### Devices

* Developers
* Test Environments
* Development Workstations

---

## VLAN 40 - Data Center

| Item              | Value         |
| ----------------- | ------------- |
| Network Address   | 10.10.40.0/24 |
| Subnet Mask       | 255.255.255.0 |
| Default Gateway   | 10.10.40.1    |
| Usable Hosts      | 254           |
| Broadcast Address | 10.10.40.255  |

### Devices

* Domain Controllers
* DNS Servers
* DHCP Servers
* File Servers
* Backup Servers
* Monitoring Servers

---

# Mombasa Branch

## VLAN 110 - Sales & Customer Support

| Item              | Value         |
| ----------------- | ------------- |
| Network Address   | 10.20.10.0/24 |
| Subnet Mask       | 255.255.255.0 |
| Default Gateway   | 10.20.10.1    |
| Usable Hosts      | 254           |
| Broadcast Address | 10.20.10.255  |

### Devices

* Customer Service Staff
* Sales Representatives
* Customer Support Workstations

---

## VLAN 120 - Field Engineers

| Item              | Value         |
| ----------------- | ------------- |
| Network Address   | 10.20.20.0/24 |
| Subnet Mask       | 255.255.255.0 |
| Default Gateway   | 10.20.20.1    |
| Usable Hosts      | 254           |
| Broadcast Address | 10.20.20.255  |

### Devices

* Field Engineers
* Technical Support Engineers
* Deployment Laptops

---

# Kisumu Branch

## VLAN 210 - Sales & Customer Support

| Item              | Value         |
| ----------------- | ------------- |
| Network Address   | 10.30.10.0/24 |
| Subnet Mask       | 255.255.255.0 |
| Default Gateway   | 10.30.10.1    |
| Usable Hosts      | 254           |
| Broadcast Address | 10.30.10.255  |

### Devices

* Sales Staff
* Customer Support Staff
* Branch Administration

---

## VLAN 220 - Implementation Team

| Item              | Value         |
| ----------------- | ------------- |
| Network Address   | 10.30.20.0/24 |
| Subnet Mask       | 255.255.255.0 |
| Default Gateway   | 10.30.20.1    |
| Usable Hosts      | 254           |
| Broadcast Address | 10.30.20.255  |

### Devices

* Implementation Engineers
* Project Engineers
* Deployment Teams

---

# WAN Infrastructure

## Nairobi ↔ Mombasa

| Item            | Value         |
| --------------- | ------------- |
| Network Address | 10.40.10.0/24 |
| Default Gateway | 10.40.10.1    |
| Usable Hosts    | 254           |

---

## Nairobi ↔ Kisumu

| Item            | Value         |
| --------------- | ------------- |
| Network Address | 10.40.20.0/24 |
| Default Gateway | 10.40.20.1    |
| Usable Hosts    | 254           |

---

## Mombasa ↔ Kisumu (Redundancy Link)

| Item            | Value         |
| --------------- | ------------- |
| Network Address | 10.40.30.0/24 |
| Default Gateway | 10.40.30.1    |
| Usable Hosts    | 254           |

---

# Design Justification

The addressing plan follows a structured enterprise design approach.

Benefits include:

* Easy identification of branch locations.
* Easier troubleshooting.
* Scalability for future expansion.
* Simplified routing.
* Support for OSPF dynamic routing.
* Support for centralized services hosted in Nairobi Headquarters.
* Clear separation of departments through VLAN segmentation.

This addressing plan forms the foundation of the Cyberjay Enterprise WAN architecture and supports future growth of the organization across multiple regions in Kenya.

