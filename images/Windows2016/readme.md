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

<details>
<summary>📂 Click to expand DHCP Scope and Client Reservation screenshots</summary>
<br>
To automate IP address distribution and ensure stable networking across the sandbox domain environment, a robust DHCP infrastructure was deployed alongside Active Directory services.
<br><br>
Using the DHCP Management Console, a new IPv4 Scope was provisioned for the internal subnet network shown below. To prevent critical server assets from changing IP addresses dynamically, a dedicated MAC-to-IP reservation mapping was applied for the client workload. Leaving 192.168.80.1 - 192.168.80.149 for static infrastructure

<p align="center">
  <img src="dhcpscopecreation.png" alt="DHCP Scope Range Properties" width="85%"/>
  <br>
  <em>Figure 3: Configuring the IPv4 dynamic pool distribution range (192.168.80.150 - 192.168.80.254).</em>
</p>

---

<p align="center">
  <img src="dhcpreservation.png" alt="DHCP Client Reservation Active Settings" width="85%"/>
  <br>
  <em>Figure 4: Creating a persistent Reserved Client lease bound to the unique physical MAC address of the target computer (Winodws 2012)</em>
</p>

</details>
