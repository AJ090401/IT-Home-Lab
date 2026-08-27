# 🖥️ VM Setup Details & Configurations

This directory contains the core baseline configurations, resource allocations, and initial setup workflows for all virtual machines deployed across the home lab environment.

---

## 📊 Hardware & Resource Allocation
Before installing the operating systems, the virtual machines were provisioned with the following specifications to balance host performance and sandbox stability:

| VM Name | OS / Distribution | vCPUs | RAM | Storage | Primary Network Role |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **DC-01** | Windows Server 2012 R2 | 2 | 4 GB | 60 GB | Active Directory Domain Controller / DNS |
| **SRV-02** | Windows Server 2016 | 2 | 4 GB | 60 GB | Member Server / Core Infrastructure Upgrade |
| **MINT-CLI-01**| Linux Mint 21.x | 2 | 2 GB | 40 GB | Sandbox Enterprise Client / Testing Node |
