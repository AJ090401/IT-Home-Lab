# 🖥️ VM Setup Details & Configurations

This directory contains the core baseline configurations, resource allocations, and initial setup workflows for all virtual machines deployed across the home lab environment.

---

## 📊 Hardware & Resource Allocation
Before installing the operating systems, the virtual machines were provisioned with the following specifications to balance host performance and sandbox stability:

| VM Name | OS / Distribution | vCPUs | RAM | Storage |Network Adapter| Primary Network Role | IP Address |
| :--- | :--- | :--- | :--- | :--- | :--- |:---| :---|
| **Windows Server 2012 R2** | Windows Server 2012 R2 | 4 | 8 GB | 60 GB |VMnet8 (NAT)| No longer in use | 192.168.80.160 (Not in use) |
| **Fileserver2016** | Windows Server 2016 | 4 | 8 GB | 60 GB |VMnet8 (NAT)| Joined to Domain Controller (2016 File Server) | 192.168.80.150 |
| **win-agt0o9hb1rg** | Windows Server 2016 | 4 | 8 GB | 60 GB |VMnet8 (NAT)| Domain Controller (DC) | 192.168.80.132 |
| **DESKTOP-9K4VKO1** | Windows 11 | 4 | 8 GB | 60 GB |VMnet8 (NAT)| Joined to Domain Controller W11| 192.168.80.170 |
| **Linux Client** | Linux Mint | 2 | 4 GB | 20 GB | NAT |Sandbox Enterprise Client / Testing Node | N/A |
| **Penetration Testing Client** | Kali Linux | 2 | 4 GB | 20 GB | NAT |Security Assessment & Vulnerability Scanning Node | N/A |

