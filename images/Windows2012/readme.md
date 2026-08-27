# 🛠️ IT Home Lab Environment

Welcome to my enterprise home lab project. This repository documents the deployment, configuration, and management of a hybrid network environment featuring Active Directory, Windows Server, and Linux endpoints.

---

## 🖥️ Windows Server 2012 R2 Deployment

This section details the base configuration and active integration of the Windows Server 2012 R2 environment.

<details>
<summary>📂 Click to expand Active Directory Domain Join screenshots</summary>

<br>

To seamlessly integrate the server into the sandbox environment, the system hostname was standardized before completing the domain authentication sequence.

### Step 1: Configuring Computer Name and Domain Settings
Before initiating the join, the system properties were accessed to transition the server from a standalone workgroup to the target domain layout.

<p align="center">
  <img src="setupdomainjoin.png" alt="Windows Server 2012 R2 System Properties" width="85%"/>
  <br>
  <em>Figure 1: Navigating to System Properties to target the local domain environment.</em>
</p>

---

### Step 2: Successful Domain Authentication
After supplying the required administrative credentials, the server successfully negotiated entry into the infrastructure.

<p align="center">
  <img src="joiningdomain.png" alt="Domain Join Success Dialog" width="85%"/>
  <br>
  <em>Figure 2: Verifying successful domain integration with the avengers.local domain.</em>
</p>

</details>

