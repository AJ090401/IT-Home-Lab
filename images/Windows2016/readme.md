## 🛡️ Windows 2016 Server Information (avengers.local)

<details> <summary>📂 Click to expand Active Directory Management screenshots</summary> <br> To organize organization resources and manage corporate identities within the sandbox environment, a structured directory hierarchy was established before provisioning network access.<br><br>

Using Active Directory Users and Computers, a new Organizational Unit (OU) called Marketing was created. Followed by the creation of a domain user identity within that container.

<p align="center"> 
  <img src="OU&NewDomainUser.png" alt="Active Directory Users and Computers Management Console" width="85%"/> 
  <br> 
  <em>Figure 2: Creating the Marketing OU and populating it with a new user identity (avengers.local).</em> 
</p>

---

## 🌐 Windows Server DHCP Infrastructure Configuration

To automate IP address distribution and ensure stable networking across the sandbox domain environment, the DHCP Server role was installed and authorized on the Domain Controller to manage centralized dynamic allocations and persistent IP reservations.

<details>
<summary>📂 Click to expand DHCP Scope and Client Reservation screenshots</summary>
<br>

Using the DHCP Management Console, a new IPv4 Scope was provisioned for the internal subnet network (192.168.80.1 - 192.168.80.254). To prevent critical server assets from changing IP addresses dynamically, a dedicated MAC-to-IP reservation mapping was applied for the client workload, leaving 192.168.80.1 - 192.168.80.149 for static infrastructure.

<p align="center">
  <img src="DHCPScopeProperties.png" alt="DHCP Scope Range Properties" width="85%"/>
  <br>
  <em>Figure 3: Configuring the IPv4 dynamic pool distribution range (192.168.80.150 - 192.168.80.254).</em>
</p>

---

<p align="center">
  <img src="DHCPReservationDetails.png" alt="DHCP Client Reservation Active Settings" width="85%"/>
  <br>
  <em>Figure 4: Creating a persistent Reserved Client lease bound to the unique physical MAC address of the target node.</em>
</p>

</details>

### 🛠️ Network Subnet & Architecture Breakdown

The entire lab infrastructure operates within an isolated, private virtual boundary hosted on **VMware VMnet8 (NAT)**. This configuration allows the internal servers to share the host's physical network connection for internet updates while isolating core Active Directory traffic from external networks.

#### 📊 Subnet Blueprint: 192.168.80.0/24
* **Network ID:** `192.168.168.80.0`
* **Subnet Mask:** `255.255.255.0` (CIDR: `/24`)
* **Default Gateway:** `192.168.80.2` (VMware Virtual NAT Router)
* **Active Domain Name:** `avengers.local`

---

### 🗺️ IP Allocation Strategy

The network range is cleanly partitioned into two operational blocks to replicate standard real-world enterprise infrastructure deployment methodologies:

#### 1. Static Infrastructure Block (`192.168.80.1` – `192.168.80.149`)
This space is strictly excluded from automated dynamic leases. It is manually mapped to critical core systems to eliminate the risk of dynamic IP assignment shifts or lease conflicts.
* **`192.168.80.2`** – Virtual Default Gateway (Routing engine)
* **`192.168.80.132`** – Primary Domain Controller & Active Directory Integrated DNS Server

#### 2. Dynamic Client Pool (`192.168.80.150` – `192.168.80.254`)
Managed directly by the Windows DHCP Server service, this range handles on-demand networking configurations for endpoints and non-core nodes.
* **Dynamic Scopes (No Reservation):** Any newly deployed member server or end-user workstation joined to the `VMnet8` interface instantly obtains a temporary dynamic lease config.
* **Persistent Reservations:** Target nodes requiring centralized lease management alongside static consistency utilize hardware address mappings.
  * **`192.168.80.160`** – Bound exclusively to the Windows 2012 Server node via its hardware identity (`00:0c:29:42:1f:36`).

