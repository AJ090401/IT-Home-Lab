## 🛡️ Windows 2016 Server Information (avengers.local)

<details> 
<summary>📂 Click to expand Active Directory Management screenshots</summary> 
<br> 
To organize organization resources and manage corporate identities within the sandbox environment, a structured directory hierarchy was established before provisioning network access.
<br><br> 
Using Active Directory Users and Computers, a new Organizational Unit (OU) called Marketing was created. Followed by the creation of a domain user identity within that container. 

<p align="center"> 
  <img src="OU&NewDomainUser.png" alt="Active Directory Users and Computers Management Console" width="85%"/> 
  <br> 
  <em>Figure 1: Creating the Marketing OU and populating it with a new user identity (avengers.local).</em> 
</p> 

</details>

---

## 🌐 Windows Server DHCP Infrastructure Configuration

<details> 
<summary>📂 Click to expand DHCP Scope and Client Reservation screenshots</summary> 
<br> 
To automate IP address distribution and ensure stable networking across the sandbox domain environment, a robust DHCP infrastructure was deployed alongside Active Directory services. 
<br><br> 
Using the DHCP Management Console, a new IPv4 Scope was provisioned for the internal subnet network shown below. To prevent critical server assets from changing IP addresses dynamically, a dedicated MAC-to-IP reservation mapping was applied for the client workload, leaving 192.168.80.1 - 192.168.80.149 for static infrastructure.

<p align="center"> 
  <img src="dhcpscopecreation.png" alt="DHCP Scope Range Properties" width="85%"/> 
  <br> 
  <em>Figure 2: Configuring the IPv4 dynamic pool distribution range (192.168.80.150 - 192.168.80.254).</em> 
</p> 

--- 

<p align="center"> 
  <img src="dhcpreservation.png" alt="DHCP Client Reservation Active Settings" width="85%"/> 
  <br> 
  <em>Figure 3: Creating a persistent Reserved Client lease bound to the unique physical MAC address of the target computer (Windows 2012).</em> 
</p> 

</details>

---

## 💾 Enterprise Storage Access Control & GPO Drive Map Automation

<details>
<summary>📂 Click to expand Storage Security and Group Policy screenshots</summary>
<br>
To enforce role-based access control (RBAC) across the domain environment, network storage was provisioned and secured using a dual-layer authentication structure (NTFS and Share permissions) before deploying automated client drive mappings via Group Policy Preferences (GPP).

### Step 1: Security Group & Local Directory Hardening
A new global Active Directory Security Group named `Marketing-Share-AV` was provisioned within the Marketing OU, and the target domain user profile (`Mike Trout`) was nested inside it. Concurrently, a local folder structure (`C:\AvengersMarketing`) was created on the system drive. Local NTFS permissions were explicitly hardened to grant the security group **Modify, Read & Execute, List Folder Contents, Read, and Write** capabilities while stripping generic unauthenticated access.

<p align="center">
  <img src="NTFSSecuritySettings.png" alt="NTFS Folder Security Tab Configuration" width="85%"/>
  <br>
  <em>Figure 4: Hardening local NTFS directory structures to match corporate Security Group scopes.</em>
</p>

---

### Step 2: Directory Services Policy Mapping
Within the **Group Policy Management Console**, a dedicated Group Policy Object (GPO) titled **"Map Marketing Share Drive"** was generated and explicitly linked directly to the root of the **Marketing OU** container to isolate policy enforcement to targeted business units.

<p align="center">
  <img src="GPOLinkVerification.png" alt="Group Policy Management Console Linking" width="85%"/>
  <br>
  <em>Figure 5: Associating the drive mapping policy directly with the target corporate Organizational Unit.</em>
</p>

---

### Step 3: Group Policy Preference Orchestration
Using the Group Policy Management Editor, the automated workspace layout was configured strictly under the **User Configuration** preference path to prevent deployment blocks. To resolve session conflicts and bypass ghost registry locks, the execution action was elevated to **Replace**, mapping the UNC network block (`\\192.168.80.132\AvengersMarketing`) to the client profile space under the persistent drive letter identity **M:**.

<p align="center">
  <img src="GPOUserDrivePreference.png" alt="Group Policy Drive Maps Preference Configuration" width="85%"/>
  <br>
  <em>Figure 6: Deploying a 'Replace' action mapping preference under the User context path.</em>
</p>

---

### Step 4: Directory Scope Identity Hierarchy
Active Directory Users and Computers confirms the final structured deployment mapping: both the functional network user identity and the storage orchestration group exist inside the same container boundaries, ensuring flawless policy evaluation loops during client logon routines.

<p align="center">
  <img src="ADUCFinalStructure.png" alt="Active Directory Users and Computers OU Hierarchy" width="85%"/>
  <br>
  <em>Figure 7: Final structural hierarchy layout within the Marketing Organizational Unit boundary.</em>
</p>

</details>
