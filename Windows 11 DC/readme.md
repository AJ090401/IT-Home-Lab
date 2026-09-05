# Windows 11 Server Lab Documentation

## 🌐 DNS

<details>
<summary>📂 Click to expand regarding actions performed on W11</summary>
<br>

### Detailed Actions Performed

* **Dynamic Forward Lookup Registration**
  * A **Host (A)** record was automatically generated inside the primary forward lookup zone (`avengers.local`). The machine bound its unique hostname `Fileserver2016` to the dynamically assigned IP address **`192.168.80.150`**. A dynamic update lease timestamp was registered on **9/1/2026 at 6:00:00 AM**, proving live communication with the server.
  <p align="center">
    <img src="../images/forwardlookupzones.png" alt="DNS Manager Forward Lookup Zone Configuration" width="85%"/>
    <br>
    <em>Figure 1: Verifying active Host (A) records and dynamic update lease timestamps within the forward lookup zone.</em>
  </p>

* **Network Subnet & Reverse Zone Alignment**
  * The client was assigned an address within the `192.168.80.0/24` network range. This matches the exact network boundaries governed by the **Active Directory-Integrated Primary** reverse lookup zone (**`80.168.192.in-addr.arpa`**), establishing the environment for complete, two-way internal network name resolution.
  <p align="center">
    <img src="../images/reverselookupzone.png" alt="DNS Manager Reverse Lookup Zone Configuration" width="85%"/>
    <br>
    <em>Figure 2: Viewing the Active Directory-Integrated Primary reverse lookup zone configuration for the local subnet.</em>
  </p>

---
</details>

## 🛡️ Windows Defender Firewall

<details>
<summary>📂 Click to expand regarding firewall rules established on W11</summary>
<br>

### Detailed Actions Performed

* **Default Profile Hardening**
  * Configured the global ingress policy across all three network profiles (**Domain**, **Private**, and **Public**) to explicitly **Block Inbound Connections**. This ensures a default-deny posture where all unsolicited traffic is discarded by default, mitigating lateral network movement vulnerabilities.

* **Scoped Inbound Management Rules**
  * Provisioned a custom inbound firewall rule titled **`Secure VMnet8 RDP`** targeting **TCP Port 3389** to handle remote management requests. To prevent unauthorized traffic from outside the hypervisor sandbox, the remote scope of this rule was restricted explicitly to the internal subnet range (**`192.168.80.0/24`**).
  <p align="center">
    <!-- Replace the src path below with your actual firewall screenshot if you have one -->
    <img src="../images/firewallrules.png" alt="Windows Defender Firewall Inbound Rules Configuration" width="85%"/>
    <br>
    <em>Figure 3: Configuration of the scoped inbound RDP rule restricting remote access exclusively to the local virtual subnet.</em>
  </p>

---
</details>

