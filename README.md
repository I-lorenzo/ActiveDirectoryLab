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

  https://imgur.com/a/tVwAWzw

<p align="center">
Launch the utility: <br/>
<img src="https://imgur.com/QthdfWs.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
  
<p align="center">
Launch the utility: <br/>
<img src="https://imgur.com/qsFqbHX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
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

---

### 3. Organizational Structure
- Created Organizational Units (OUs):
  - Users
  - Groups
  - Computers
- Added test users and groups
- Applied consistent naming conventions

---

### 4. PowerShell Automation 💡
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

```powershell
param (
    [Parameter(Mandatory=$true)]
    [string]$FirstName,

    [Parameter(Mandatory=$true)]
    [string]$LastName,

    [Parameter(Mandatory=$true)]
    [string]$UserName,

    [Parameter(Mandatory=$true)]
    [string]$OU,

    [Parameter(Mandatory=$true)]
    [string]$Domain
)

# Example logic (simplified)
$Password = ConvertTo-SecureString "P@ssw0rd123" -AsPlainText -Force

New-ADUser `
    -Name "$FirstName $LastName" `
    -GivenName $FirstName `
    -Surname $LastName `
    -SamAccountName $UserName `
    -UserPrincipalName "$UserName@$Domain" `
    -Path $OU `
    -AccountPassword $Password `
    -Enabled $true

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
