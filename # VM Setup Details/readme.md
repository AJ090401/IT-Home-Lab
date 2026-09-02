# 🖥️ VM Setup Details & Configurations

This directory contains the core baseline configurations, resource allocations, and initial setup workflows for all virtual machines deployed across the home lab environment.

---

## 📊 Hardware & Resource Allocation
Before installing the operating systems, the virtual machines were provisioned with the following specifications to balance host performance and sandbox stability:

| VM Name / Role | OS / Distribution | vCPUs | RAM | Storage |Network Adapter| Primary Network Role |
| :--- | :--- | :--- | :--- | :--- | :--- |:---|
| **Windows Server 2012 R2** | Windows Server 2012 R2 | 4 | 8 GB | 60 GB |VMnet8 (NAT)| No longer in use |
| **WServer 2016 File Sharing** | Windows Server 2016 | 4 | 8 GB | 60 GB |VMnet8 (NAT)| Joined to Domain Controller (2016 File Server) |
| **WServer 2016 DC** | Windows Server 2016 | 4 | 8 GB | 60 GB |VMnet8 (NAT)| Domain Controller (DC) |
| **Windows 11 Server** | Windows 11 Server | 4 | 8 GB | 60 GB |VMnet8 (NAT)| 2nd Domain Controller (DC) |
| **Linux Client** | Linux Mint | 2 | 4 GB | 20 GB | NAT |Sandbox Enterprise Client / Testing Node |
| **Penetration Testing Client** | Kali Linux | 2 | 4 GB | 20 GB | NAT |Security Assessment & Vulnerability Scanning Node |

