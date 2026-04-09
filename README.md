# 🖥️ Active Directory Home Lab (TCM Security)

## 📌 Overview
This project demonstrates the setup and configuration of a fully functional **Active Directory lab environment** using virtual machines. It simulates a real-world enterprise network, including domain services, user management, and automation with PowerShell.

---

## ⚙️ Technologies Used
- Windows Server (Domain Controller)
- Windows 10/11 (Client Machine)
- Active Directory Domain Services (AD DS)
- PowerShell
- VirtualBox / VMware
- DNS & DHCP

---

## 🧱 Project Setup

### 1. Environment Setup
- Installed virtualization software (VirtualBox / VMware)
- Created two virtual machines:
  - Domain Controller (Windows Server)
  - Client Machine (Windows 10/11)
- Configured both machines on the same internal network


<p align="center">
Launch the utility: <br/>
<img src="https://imgur.com/G81L1EE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
  
---

### 2. Domain Controller Configuration
- Installed Active Directory Domain Services (AD DS)
- Promoted server to Domain Controller
- Created domain: `lab.local`
- Configured DNS during setup
  
<p align="center">
Launch the utility: <br/>
<img src="https://imgur.com/sIECu0q.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<p align="center">
Launch the utility: <br/>
<img src="https://imgur.com/JVZTS3I.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<p align="center">
Launch the utility: <br/>
<img src="https://imgur.com/ONktJa5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

<p align="center">
Launch the utility: <br/>
<img src="https://imgur.com/QthdfWs.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
  
<p align="center">
Launch the utility: <br/>
<img src="https://imgur.com/qsFqbHX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

<p align="center">
Launch the utility: <br/>
<img src="https://imgur.com/RdMTDrt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<p align="center">
Launch the utility: <br/>
<img src="https://imgur.com/Yp0wJX2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

---

### 3. Organizational Structure
- Created Organizational Units (OUs):
  - Users
  - Groups
  - Computers
- Added test users and groups
- Group Policy background
- Group Policy background lock


<p align="center">
Launch the utility: <br/>
<img src="https://imgur.com/Imcxert.png" height="80%" width="80%" alt="Organizational Structure"/>
<br />
  
<p align="center">
Launch the utility: <br/>
<img src="https://imgur.com/V6pvH17.png" height="80%" width="80%" alt="Organizational Structure"/>
<br />

<p align="center">
Launch the utility: <br/>
<img src="https://imgur.com/NPr0k17.png" height="80%" width="80%" alt="Organizational Structure"/>
<br />
  
<p align="center">
Launch the utility: <br/>
<img src="https://imgur.com/8iL8yBD.png" height="80%" width="80%" alt="Organizational Structure"/>
<br />

<p align="center">
Launch the utility: <br/>
<img src="https://imgur.com/D79k6jt.png" height="80%" width="80%" alt="Organizational Structure"/>
<br />

---

## 📁 File Sharing & Permissions

### 4. Shared Folder Configuration
- Created a shared folder on the Domain Controller
- Configured permissions
- Assigned access based on user roles/groups
- Restricted unauthorized access

<p align="center">
Launch the utility: <br/>
<img src="https://imgur.com/ia2Aggi.png" height="80%" width="80%" alt="Shared Folder Configuration"/>
<br />
  
<p align="center">
Launch the utility: <br/>
<img src="https://imgur.com/EbM6eMF.png" height="80%" width="80%" alt="Shared Folder Configuration"/>
<br />

<p align="center">
Launch the utility: <br/>
<img src="https://imgur.com/Ezp60gZ.png" height="80%" width="80%" alt="Shared Folder Configuration"/>
<br />

### 4. Network Drive Mapping
- From Windows 11 client:
  - Connected to shared folder via network path 
  - Mapped the shared folder as a network drive
- Enabled persistent drive mapping for user sessions

<p align="center">
Launch the utility: <br/>
<img src="https://imgur.com/EyRWejh.png" height="80%" width="80%" alt="Drive Mapping"/>
<br />
  
<p align="center">
Launch the utility: <br/>
<img src="https://imgur.com/hzNJmOA.png" height="80%" width="80%" alt="Drive Mapping"/>
<br />

### 5. Access Control Testing
- Verified access using different domain user accounts:
  - Confirmed read/write permissions
  - Tested restricted users (access denied scenarios)

<p align="center">
Launch the utility: <br/>
<img src="https://imgur.com/ee7n8yI.png" height="80%" width="80%" alt="users"/>
<br />
  
---

### 7. PowerShell Automation 💡
Developed a PowerShell script to automate user creation.

#### Features:
- Accepts input parameters:
  - First Name
  - Last Name
  - Username
  - OU
  - Domain
- Creates Active Directory users
- Assigns users to correct OU
- Sets default password
- Enables accounts

<p align="center">
Launch the utility: <br/>
<img src="https://imgur.com/RNlco8a.png" height="80%" width="80%" alt="PowerShell script"/>
<br />
  
<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
