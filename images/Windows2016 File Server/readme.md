# Windows 2016 File Server

## 🖥️ Windows 2016 File Server Integration

<details> 
<summary>📂 Click to view more regarding the Share creation</summary> 
<br> 
  
To provision centralized storage for the network, an SMB file share named **AvengersFiles** was created on the `FILESERVER2016` member server. This share points locally to `E:\Shares\AvengersFiles` and contains dedicated folders for each department. This E drive was created another NVMe hard disk with 20GB


--- 

<br> 

Using Group Policy Management, a drive mapping policy was configured to automatically mount this directory for authorized users. When a member of the Fire Department group, such as **Ken Griffey**, logs into a domain workstation, Group Policy automatically maps the **AvengersFireDepartment** network location directly to their file explorer.

Inside the `E:\Shares\AvengersFiles` directory, department-specific folders were created, each containing a security group and 1-2 users in each security group 

Using Group Policy Preferences (GPP) for Drive Mapping, a GPO was deployed to automate the connection of this network path for authenticated users. When a member of the fire department group such as user **Ken Griffey**—logs into a domain-joined workstation, the **AvengersFireDepartment** drive is automatically mounted and made available under "Network locations" in their file explorer.
</details>
