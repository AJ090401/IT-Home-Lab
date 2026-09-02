# Windows 11 Server Lab Documentation

## 🖥️ Windows 11 Integration

<details>
<summary>📂 Click to view more regarding actions performed on W11</summary>
<br>

### Overview of Active Directory & DNS Actions
The Windows 11 client machine **DESKTOP-9K4VKO1** was integrated into the enterprise lab environment running under the **avengers.local** domain infrastructure. The system automatically communicated its network profile to the primary Domain Controller (**win-agt0o9hb1rg**), registering its identity across the forwarding database.

### Detailed Actions Performed

* **Domain Authentication & Join**
  * The Windows 11 machine was successfully authenticated against Active Directory and converted from a local Workgroup configuration into a member workstation of the `avengers.local` domain (documented in `images/joiningdomain.png` and `images/setupdomainjoin.png`).

* **Dynamic Forward Lookup Registration**
  * A **Host (A)** record was automatically generated inside the primary forward lookup zone (`avengers.local`), as illustrated in `images/forwardlookupzone.png`.
  * The machine bound its unique hostname `DESKTOP-9K4VKO1` to the dynamically assigned IP address **`192.168.80.170`**.
  * A dynamic update lease timestamp was registered on **9/1/2026 at 4:00:00 PM**, proving that the client machine is actively refreshing its status and maintaining live communication with the DNS server (documented in `images/successfulsignin.png`).

* **Network Subnet & Reverse Zone Alignment**
  * The client was assigned an address within the `192.168.80.0/24` network range via the DHCP scope arrangement (documented in `images/dhcpscopecreation.png` and `images/successfuldhcpreservation.png`).
  * This matches the exact network boundaries governed by the **Active Directory-Integrated Primary** reverse lookup zone (**`80.168.192.in-addr.arpa`**), visible in `images/reverselookupzone.png`, setting up the environment for complete, two-way internal network name resolution.

---
</details>
