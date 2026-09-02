# 🖥️ VM Setup Details & Configurations

This directory contains the core baseline configurations, resource allocations, and initial setup workflows for all virtual machines deployed across the home lab environment.

---

## 📊 Hardware & Resource Allocation
Before installing the operating systems, the virtual machines were provisioned with the following specifications to balance host performance and sandbox stability:

| VM Name | OS / Distribution | vCPUs | RAM | Storage |Network Adapter| Primary Network Role |
| :--- | :--- | :--- | :--- | :--- | :--- |:---|
| **Windows Server 2012 R2** | Windows Server 2012 R2 | 4 | 8 GB | 60 GB |VMnet8 (NAT)| No longer in use | 
| **Fileserver2016** | Windows Server 2016 | 4 | 8 GB | 60 GB |VMnet8 (NAT)| Joined to Domain Controller (2016 File Server) |
| **win-agt0o9hb1rg** | Windows Server 2016 | 4 | 8 GB | 60 GB |VMnet8 (NAT)| Domain Controller (DC) | 
| **DESKTOP-9K4VKO1** | Windows 11 | 4 | 8 GB | 60 GB |VMnet8 (NAT)| Joined to Domain Controller W11|
| **Linux Client** | Linux Mint | 2 | 4 GB | 20 GB | NAT |Sandbox Enterprise Client / Testing Node |
| **Penetration Testing Client** | Kali Linux | 2 | 4 GB | 20 GB | NAT |Security Assessment & Vulnerability Scanning Node |

