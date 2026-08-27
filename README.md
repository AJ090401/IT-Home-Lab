# IT Home Lab

A collection of virtual IT labs I built to develop hands-on experience with Windows Server, Active Directory, DNS, networking, and system administration.

## Labs

- Active Directory / Domain Controller
- DNS & DHCP
- Windows Client/Server Administration
- Networking & Troubleshooting
- Linux Mint Practice Activities 

## Skills Practiced

- Windows Server
- Active Directory
- Linux
- DNS
- DHCP
- TCP/IP
- User & Group Management
- Virtual Machines
- Troubleshooting




## 🌐 Active Directory Domain Join (Windows Server 2012 R2)

This section documents the process of changing the computer name and successfully joining the server to the local Active Directory domain.

### Step 1: Configuring Computer Name and Domain Settings
Before joining, the system properties were opened to assign a static environment name and target the local domain.

<p align="center">
  <img src="images/Windows2012/setupdomainjoin.png" alt="Windows Server 2012 R2 System Properties and Computer Name Domain Changes window" width="85%"/>
  <br>
  <em>Figure 1: Navigating to System Properties to change the Workgroup to the target domain.</em>
</p>

---

### Step 2: Successful Domain Authentication
After entering the administrative credentials, the server successfully joined the environment.

<p align="center">
  <img src="images/Windows2012/joiningdomain.png" alt="Computer Name Domain Changes dialog box showing Welcome to the avengers local domain message" width="85%"/>
  <br>
  <em>Figure 2: Verifying successful authentication and domain integration with the avengers.local domain.</em>
</p>
