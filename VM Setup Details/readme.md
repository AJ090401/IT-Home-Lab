# 🖥️ VM Setup Details & Configurations

This directory contains the core baseline configurations, resource allocations, and initial setup workflows for all virtual machines deployed across the home lab environment.

---

## 📊 Hardware & Resource Allocation
Before installing the operating systems, the virtual machines were provisioned with the following specifications to balance host performance and sandbox stability:

| VM Name / Role | OS / Distribution | vCPUs | RAM | Storage | Primary Network Role |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Windows Server 2012 R2** | Windows Server 2012 R2 | 4 | 8 GB | 60 GB | Joined to Domain Controller (2016 Server) |
| **Windows Server 2016** | Windows Server 2016 | 4 | 8 GB | 60 GB | Domain Controller |
| **Linux Client** | Linux Mint | 2 | 4 GB | 20 GB | Sandbox Enterprise Client / Testing Node |
| **Penetration Testing Client** | Kali Linux | 2 | 4 GB | 20 GB | Security Assessment & Vulnerability Scanning Node |

