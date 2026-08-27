# 🖥️ VM Setup Details & Configurations

This directory contains the core baseline configurations, resource allocations, and initial setup workflows for all virtual machines deployed across the home lab environment.

---

## 📊 Hardware & Resource Allocation
Before installing the operating systems, the virtual machines were provisioned with the following specifications to balance host performance and sandbox stability:

| VM Name / Role | OS / Distribution | vCPUs | RAM | Storage | Primary Network Role |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Windows Server 2012 R2** | Windows Server 2012 R2 | 4 | 4 GB | 60 GB | Primary Active Directory Domain Controller |
| **Windows Server 2016** | Windows Server 2016 | 4 | 4 GB | 60 GB | Secondary Domain Controller / Infrastructure Upgrade |
| **Linux Client** | Linux Mint | 4 | 2 GB | 20 GB | Sandbox Enterprise Client / Testing Node |

