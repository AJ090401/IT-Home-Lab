# Windows 2016 File Server

## 🖥️ Windows 2016 File Server Integration

<details> 
<summary>📂 Click to view more regarding the Share creation</summary> 
<br> 

To ensure seamless name resolution and connectivity for the newly authenticated member server (`FILESERVER2016`), authoritative Host (A) and Pointer (PTR) records were provisioned within the Domain Controller's DNS environment. 

--- 

<br> 

This ensures that users can map and connect to the network share using the server's host name instead of the IP address

Inside the `E:\Shares\AvengersFiles` directory, department-specific folders were created, each containing a security group and 1-2 users in each security group 

Using Group Policy Preferences (GPP) for Drive Mapping, a GPO was deployed to automate the connection of this network path for authenticated users. When a member of the fire department group such as user **Ken Griffey**—logs into a domain-joined workstation, the **AvengersFireDepartment** drive is automatically mounted and made available under "Network locations" in their file explorer.
</details>
