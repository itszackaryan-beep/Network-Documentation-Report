# 🖧 Network Documentation Report

**Small Network Topology Design, Port Mapping, Service Identification, and Security Assessment**

[![Platform](https://img.shields.io/badge/platform-VMware%20Workstation-blue)]()
[![Type](https://img.shields.io/badge/type-Academic%20%2F%20Lab%20Project-lightgrey)]()
[![Status](https://img.shields.io/badge/status-completed-brightgreen)]()

> A personal lab project documenting a small virtual network of four machines — network
> topology, IP configuration, open ports, running services, and a basic security
> assessment with recommendations.

**Author:** Sumit Kumar

---

## 📖 Table of Contents

1. [Introduction](#1-introduction)
2. [Objective](#2-objective)
3. [Tools Used](#-tools-used)
4. [Network Topology Design](#3-network-topology-design)
5. [Device Inventory](#4-device-inventory)
6. [IP Address Configuration](#5-ip-address-configuration)
7. [Port and Service Mapping](#6-port-and-service-mapping)
8. [Security Assessment](#7-security-assessment)
9. [Security Recommendations](#8-security-recommendations)
10. [Conclusion](#9-conclusion)
11. [Screenshots](#-screenshots)
12. [Folder Structure](#-folder-structure)

---

## 🧰 Tools Used

1. VMware Workstation
2. Windows Server 2022
3. Kali Linux
4. Ubuntu Linux
5. Windows 7
6. Command Prompt
7. Terminal

---

## 1. Introduction

This report documents a small virtual network environment consisting of four virtual
machines: **Windows Server 2022**, **Kali Linux**, **Ubuntu Linux**, and **Windows 7**. The
network topology, device configurations, open ports, services, and potential security
weaknesses were analyzed and documented.

## 2. Objective

The objective of this project is to:

- Design a small network topology
- Identify network devices
- Map open ports and running services
- Document potential security weaknesses
- Provide security recommendations

---

## 3. Network Topology Design

**Figure 1: Network Topology Diagram**

```
                    VMware Virtual Network
                            |
        ------------------------------------------------
        |                |               |             |
   Windows Server    Kali Linux       Ubuntu       Windows 7
       2022
```

**Figure 1 — VMware Virtual Network Environment**

![VMware Virtual Network Environment](docs/Screenshots/fig01-vmware-virtual-network-environment.jpg)

**Description:** The VMware Workstation environment contains four virtual machines:
Windows Server 2022, Kali Linux, Ubuntu Linux, and Windows 7. These systems are
configured within a shared virtual network for communication, testing, and network
analysis activities.

---

## 4. Device Inventory

| Device Name | Operating System | Purpose |
|---|---|---|
| Windows Server | Windows Server 2022 | Server |
| Kali Linux | Kali Linux | Security Testing |
| Ubuntu | Ubuntu Linux | Linux Workstation |
| Windows 7 | Windows 7 | Legacy Client |

**Description:** The network contains four devices used for administration, testing, and
communication purposes.

---

## 5. IP Address Configuration

### Figure 2 — Windows Server 2022 IP Configuration

![Windows Server 2022 IP Configuration](docs/Screenshots/fig02-windows-server-2022-ip-configuration.jpg)

**Description:** IP configuration information obtained using the `ipconfig` command.

### Figure 3 — Windows 7 IP Configuration

![Windows 7 IP Configuration](docs/Screenshots/fig03-windows-7-ip-configuration.jpg)

**Description:** IP configuration information obtained using the `ipconfig` command.

### Figure 4 — Kali Linux IP Configuration

![Kali Linux IP Configuration](docs/Screenshots/fig04-kali-linux-ip-configuration.jpg)

**Description:** IP configuration information obtained using the `ip a` command.

### Figure 5 — Ubuntu Linux IP Configuration

![Ubuntu Linux IP Configuration](docs/Screenshots/fig05-ubuntu-linux-ip-configuration.jpg)

**Description:** IP configuration information obtained using the `ip a` command.

### Device IP Address Summary

| Device | IP Address |
|---|---|
| Kali | xxx.xxx.xxx.xxx |
| Ubuntu | xxx.xxx.xxx.xxx |
| Windows 7 | xxx.xxx.xxx.xxx |
| Windows Server | xxx.xxx.xxx.xxx |

> IP addresses are masked in the original report (`xxx.xxx.xxx.xxx`) and are reproduced
> here exactly as documented.

---

## 6. Port and Service Mapping

### Figure 6 — Windows Server Open Ports

![Windows Server Open Ports](docs/Screenshots/fig06-windows-server-open-ports.jpg)

**Command Used:**
```powershell
netstat -ano
```

**Description:** The `netstat -ano` command was executed on Windows Server 2022 to
identify active TCP and UDP connections, listening ports, and associated process IDs.
Several network services were observed running on the system. The command displays
active network connections, listening ports, and associated process identifiers.

### Figure 7 — Kali Linux Open Ports

![Kali Linux Open Ports](docs/Screenshots/fig07-kali-linux-open-ports.jpg)

**Command Used:**
```bash
ss -tuln
```

**Description:** The `ss -tuln` command was executed on Kali Linux to identify active
TCP and UDP listening ports. The output displays network services currently available on
the system.

### Figure 8 — Ubuntu Open Ports

![Ubuntu Open Ports](docs/Screenshots/fig08-ubuntu-open-ports.jpg)

**Command Used:**
```bash
ss -tuln
```

**Description:** The `ss -tuln` command was executed on Ubuntu to identify active TCP
and UDP listening ports. The output displays network services currently available on
the system.

### Device / Port / Service Table

| Device | Port | Service |
|---|---|---|
| Windows Server | 3389 | RDP |
| Windows Server | 445 | SMB |
| Ubuntu | 22 | SSH |
| Windows 7 | 139 | NetBIOS |

### Port and Service Summary

| Port | Protocol | Service |
|---|---|---|
| 22 | TCP | SSH |
| 53 | UDP | DNS |
| 80 | TCP | HTTP |
| 443 | TCP | HTTPS |
| 3389 | TCP | Remote Desktop (RDP) |

**Description:** The identified ports indicate commonly used network services available
within the environment.

---

## 7. Security Assessment

### Potential Weak Point 1 – Legacy Operating System
Windows 7 is no longer supported and does not receive regular security updates. This
increases the risk of exploitation through known vulnerabilities.

### Potential Weak Point 2 – Open Network Ports
Open ports expose services that may be targeted by attackers if not properly secured.

### Potential Weak Point 3 – Weak Authentication
Weak or reused passwords may allow unauthorized access to network resources.

### Potential Weak Point 4 – Unencrypted Communication
Services using HTTP instead of HTTPS may expose sensitive information during
transmission.

### Potential Weak Point 5 – Firewall Misconfiguration
Improper firewall settings can allow unnecessary network access and increase attack
surface.

---

## 8. Security Recommendations

To improve the security of the network environment:

- Keep operating systems updated.
- Replace unsupported operating systems such as Windows 7.
- Enable host-based firewalls on all systems.
- Use strong passwords and account lockout policies.
- Disable unnecessary services and ports.
- Use encrypted protocols such as HTTPS and SSH.
- Regularly monitor network activity and logs.

---

## 9. Conclusion

The network documentation project was completed successfully. A virtual network
consisting of Windows Server 2022, Kali Linux, Ubuntu Linux, and Windows 7 was documented
and analyzed. Device configurations, open ports, and active services were identified.
Potential security weaknesses were evaluated, and recommendations were provided to
improve the overall security posture of the environment.

---

## 🖼️ Screenshots

All figures referenced in this report are available in [`docs/Screenshots/`](docs/Screenshots/):

| Figure | File |
|---|---|
| Figure 1 – VMware Virtual Network Environment | `docs/Screenshots/fig01-vmware-virtual-network-environment.jpg` |
| Figure 2 – Windows Server 2022 IP Configuration | `docs/Screenshots/fig02-windows-server-2022-ip-configuration.jpg` |
| Figure 3 – Windows 7 IP Configuration | `docs/Screenshots/fig03-windows-7-ip-configuration.jpg` |
| Figure 4 – Kali Linux IP Configuration | `docs/Screenshots/fig04-kali-linux-ip-configuration.jpg` |
| Figure 5 – Ubuntu Linux IP Configuration | `docs/Screenshots/fig05-ubuntu-linux-ip-configuration.jpg` |
| Figure 6 – Windows Server Open Ports | `docs/Screenshots/fig06-windows-server-open-ports.jpg` |
| Figure 7 – Kali Linux Open Ports | `docs/Screenshots/fig07-kali-linux-open-ports.jpg` |
| Figure 8 – Ubuntu Open Ports | `docs/Screenshots/fig08-ubuntu-open-ports.jpg` |

---

## 📁 Folder Structure

```
Network-Documentation-Report/
│
├── README.md
├── LICENSE
├── .gitignore
│
└── docs/
    ├── Network_Documentation_Report.pdf   # Original full report
    └── Screenshots/                       # Figures 1–8 extracted from the report
```

---

## 👤 Author

**Sumit Kumar**

Academic / personal lab project built using VMware Workstation to practice network
documentation, port and service mapping, and basic security assessment.
