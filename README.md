## Networkwalks Cybersecurity Internship - Lab 1 (setup)

## Lab 1: Lab Environment & Network Configuration

The core objective was to build a practical, isolated lab environment centered around **Kali Linux** as our primary cybersecurity toolkit, alongside companion virtual machines, to serve as the foundation for all upcoming hands-on security and practical labs.

### 1. NAT Network Configuration
To ensure controlled communication between virtual machines while maintaining external internet access, a dedicated NAT Network was configured in Oracle VM VirtualBox:
- **NAT Network Name:** `NatNetwork`
- **Network CIDR:** `10.0.0.0/24`
- **Default Gateway:** `10.0.0.1`
- **DHCP Server:** Enabled

---

### 2. Virtual Machines Topology & IP Table
| Virtual Machine | Operating System | Network Adapter Type | IP Address & Type |
| :--- | :--- | :--- | :--- |
| **Kali Linux** | Linux (Debian-based) | Attached to NAT Network | `10.0.0.2` (Static) |
| **Windows 10** | Windows | Attached to NAT Network | `10.0.0.10` (Static) |
| **Android VM** | Android | Attached to NAT Network | `10.0.0.4` (Dynamic - DHCP) |

---

### 3. Troubleshooting & Connectivity Verification

#### Step A: Resolving Windows Firewall ICMP Blocking
By default, Windows Defender Firewall blocks incoming ICMP (Ping) echo requests. To enable packet flow and troubleshooting across the lab, custom inbound rules (`ICMPv4-In`) were configured:
<br>
<img src="Screenshots/11.%20customize%20Inbound%20rule.PNG" width="450" alt="Customize Inbound Rule">

#### Step B: Full Lab Connectivity & Internet Access
Verifying complete network connectivity from our primary penetration testing machine (Kali Linux) to both the internal lab nodes and the external internet:
<br>
<img src="Screenshots/13. ICMP reply from Android to Kali.png" width="450" alt="Kali Network and Internet Verification">

---

## Key Takeaways
- **Hypervisor & Routing:** Deep understanding of VirtualBox NAT engine mechanics.
- **Firewall Troubleshooting:** Overcoming Windows Defender Firewall packet filtering restrictions (`ICMPv4-In`) to establish reliable cross-OS communication.
- **Core Realization:** A solid network foundation and the ability to manually troubleshoot traffic flows are the absolute core of effective cybersecurity.

---
**Author:** Furat Omer  
