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
