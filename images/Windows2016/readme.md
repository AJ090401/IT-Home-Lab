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
