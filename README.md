# Small Enterprise Network — VLAN Segmentation & Inter-VLAN Routing

## 📌 Project Overview

This project demonstrates the design and implementation of a small enterprise network using **Cisco Packet Tracer**.

The network represents three departments — **Human Resources (HR), Information Technology (IT), and Finance** — using separate VLANs. **IEEE 802.1Q trunking** and **Router-on-a-Stick** are implemented to enable communication between the VLANs.

A troubleshooting scenario is also included in which an incorrect VLAN encapsulation value was introduced, identified, corrected, and verified.

## 🖥️ Network Topology

The topology consists of:

* 1 × Cisco 2911 Router
* 1 × Cisco 2960 Switch
* 6 × PCs
* 3 × VLANs

### VLAN Design

| VLAN | Department | Network         | Gateway      |
| ---- | ---------- | --------------- | ------------ |
| 10   | HR         | 192.168.10.0/24 | 192.168.10.1 |
| 20   | IT         | 192.168.20.0/24 | 192.168.20.1 |
| 30   | Finance    | 192.168.30.0/24 | 192.168.30.1 |

## 🔧 Technologies & Concepts

* Cisco Packet Tracer
* Cisco IOS
* IPv4 Addressing
* VLAN Segmentation
* Access Ports
* IEEE 802.1Q Trunking
* Router-on-a-Stick
* Inter-VLAN Routing
* Network Verification
* Network Troubleshooting

## ⚙️ Configuration

### Switch Configuration

The Cisco 2960 switch was configured with three VLANs and access ports for each department.

The connection between **SW1 Fa0/1** and **R1 G0/0** was configured as an IEEE 802.1Q trunk.

The complete switch configuration is available in:

`Configuration/switch-config.txt`

### Router Configuration

Router subinterfaces were configured to provide the default gateway for each VLAN and enable inter-VLAN routing.

The complete router configuration is available in:

`Configuration/router-config.txt`

## 🧪 Verification & Testing

The network was verified using Cisco IOS commands including:

* `show vlan brief`
* `show interfaces trunk`
* `show ip interface brief`
* `show running-config`

Connectivity was tested using ICMP ping between:

* Devices within the same VLAN
* Devices across different VLANs

Successful inter-VLAN communication was achieved through the Router-on-a-Stick configuration.

## 🛠️ Troubleshooting Case Study

A deliberate configuration error was introduced on the **VLAN 20 router subinterface**.

The correct configuration:

```text
encapsulation dot1Q 20
```

was changed to:

```text
encapsulation dot1Q 25
```

This caused inter-VLAN connectivity to fail.

The incorrect configuration was identified and corrected by changing the VLAN ID back to **20**. Connectivity was then successfully restored.

## 📸 Screenshots

The `Screenshots` folder contains evidence of:

1. Network topology
2. VLAN verification
3. Trunk verification
4. Router interface verification
5. Same-VLAN connectivity
6. Inter-VLAN connectivity
7. Incorrect configuration
8. Connectivity failure
9. Configuration correction
10. Successful connectivity after correction

## 📚 Learning Outcomes

Through this project, I practiced:

* Designing a basic enterprise network topology
* Segmenting a network using VLANs
* Configuring switch access ports
* Configuring IEEE 802.1Q trunking
* Implementing Router-on-a-Stick
* Configuring inter-VLAN routing
* Verifying network operation using Cisco IOS commands
* Diagnosing and correcting a VLAN configuration problem

## 🚀 Future Development

Future projects will extend this foundation toward more advanced **network engineering and network security** concepts, including:

* OSPF
* DHCP
* ACLs
* NAT
* Secure device management using SSH
* Firewall concepts
* VPNs
* Network automation
* Linux networking
* Cloud networking and security

---

**Project Type:** Cisco Networking / Enterprise Networking
**Platform:** Cisco Packet Tracer
**Focus:** Network Engineering with Network Security
