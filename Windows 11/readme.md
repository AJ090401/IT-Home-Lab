# Windows 11 Server Lab Documentation

## 🖥️ Windows 11 Integration

<details>
<summary>📂 Click to view more regarding actions performed on W11</summary>
<br>

### Overview of Active Directory & DNS Actions
The Windows 11 client machine **DESKTOP-9K4VKO1** was integrated into the enterprise lab environment running under the **avengers.local** domain infrastructure. The system automatically communicated its network profile to the primary Domain Controller (**win-agt0o9hb1rg**), registering its identity across the forwarding database.

### Detailed Actions Performed

* **Dynamic Forward Lookup Registration**
  * A **Host (A)** record was automatically generated inside the primary forward lookup zone (`avengers.local`), which is visually documented in `images/forwardlookupzone.png`.
  * The machine bound its unique hostname `DESKTOP-9K4VKO1` to the dynamically assigned IP address **`192.168.80.170`**.
  * A dynamic update lease timestamp was registered on **9/1/2026 at 4:00:00 PM**, proving that the client machine is actively refreshing its status and maintaining live communication with the DNS server.

* **Network Subnet & Reverse Zone Alignment**
  * The client was assigned an address within the `192.168.80.0/24` network range.
  * This matches the exact network boundaries governed by the **Active Directory-Integrated Primary** reverse lookup zone (**`80.168.192.in-addr.arpa`**), which is visually documented in `images/reverselookupzone.png`. This configuration establishes the environment for complete, two-way internal network name resolution.

---
</details>
