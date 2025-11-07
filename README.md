# 🪟 Windows Active Directory Lab (Server 2019)

This project demonstrates the full deployment of a **Windows Server 2019 Active Directory Domain Services (AD DS)** environment in a virtual lab.  
It simulates a small enterprise domain setup complete with DNS integration, organizational structure, user management, and Group Policy implementation.

---

## 🧠 Overview

| **Category** | **Details** |
|---------------|-------------|
| **Platform** | VirtualBox / VMware Workstation |
| **Server OS** | Windows Server 2019 Standard (Evaluation) |
| **Roles Installed** | AD DS, DNS Server |
| **Domain Name** | `jcb.local` |
| **Goal** | Build, configure, and manage a basic Active Directory domain in a self-contained lab |

---

## ⚙️ Key Objectives

- 🧩 Install and configure **Windows Server 2019**
- 🌐 Assign a **static IPv4 address** and local DNS
- 🏛️ Install **Active Directory Domain Services (AD DS)** and **DNS**
- 🚀 Promote the server to a **Domain Controller**
- 👥 Create **Organizational Units (OUs)** and **user accounts**
- 🔐 Configure **Group Policy Objects (GPOs)** for password complexity and domain policies

---

## 🗺️ Step-by-Step Deployment

### **1️⃣ Install Windows Server**
A clean installation of Windows Server 2019 from ISO media inside VMware/VirtualBox.  
Set Administrator credentials during setup.

![Installing Windows](images/01-installing-windows.png)

---

### **2️⃣ Set the Local Administrator Password**
Define a secure Administrator password during initial configuration.

![Admin password](images/02-admin-password.png)

---

### **3️⃣ First Login**
Login using the Administrator credentials to access the desktop and Server Manager.

![First login](images/03-first-login.png)

---

### **4️⃣ Launch Server Manager**
Server Manager is the main interface for configuring system roles, features, and networking.

![Server Manager](images/04-server-manager.png)

---

### **5️⃣ Configure a Static IPv4 Address**
A static IP ensures consistent DNS resolution and domain reliability.  
Example configuration:
- IP Address: `192.168.1.100`  
- Subnet Mask: `255.255.255.0`  
- Default Gateway: `192.168.1.1`  
- Preferred DNS: `127.0.0.1` (or same server IP)

![Static IP config](images/05-static-ip-config.png)

---

### **6️⃣ Rename the Server**
Rename the host for easier identification (e.g., `JCB-MattDC`).  
Restart the machine after renaming.

![Server name](images/06-server-name.png)

---

### **7️⃣ Add Server Roles: AD DS + DNS**
Use the “Add roles and features” wizard to install:
- **Active Directory Domain Services**
- **DNS Server**
- **Group Policy Management**

![Installing AD DS](images/07-installing-ad-ds.png)

---

### **8️⃣ Confirm Role Installation**
Ensure that the roles were installed successfully before proceeding.

![AD DS installed](images/08-ad-ds-installed.png)

---

### **9️⃣ DNS Options (Delegation Warning)**
A common warning appears in standalone labs:  
> “A delegation for this DNS server cannot be created…”  
This is safe to ignore in single-domain setups.

![DNS options](images/09-dns-options.png)

---

### **🔟 DNS Post-Install Warnings**
Review informational messages related to IPv6 and delegation.  
Static IP configuration resolves most of these.

![DNS warnings](images/10-dns-warnings.png)

---

### **1️⃣1️⃣ Create Organizational Units and Users**
After the server is promoted to a Domain Controller and rebooted, open **Active Directory Users and Computers (ADUC)**.  
Organize departments (Accounting, Sales, Production, Management, Admins) and add test users.

Example OUs and users:
- `Accounting`: Alice Miller, Bob Clark  
- `Sales`: Charlie Davis, Diana Evans  
- `Management`: Kevin Lewis, Laura Martin  
- `Admins`: Ian Jones, Julia King  

![Users and Groups](images/11-users-and-groups.png)

---

### **1️⃣2️⃣ Verify AD DS and DNS Health**
Check Server Manager dashboard to confirm **green status** on AD DS and DNS roles.

![Dashboard](images/12-dashboard.png)

---

### **1️⃣3️⃣ Create a Group Policy Object (GPO)**
Use **Group Policy Management** to create a new domain-linked GPO named:
> “JCB Password Policy”

![Create GPO](images/13-create-gpo.png)

---

### **1️⃣4️⃣ Configure Password Policy**
Edit the GPO under:
> Computer Configuration → Policies → Windows Settings → Security Settings → Account Policies → Password Policy

Set:
- Minimum password length: 8 characters  
- Enforce password history: 5 passwords remembered  
- Maximum password age: 60 days  
- Password must meet complexity requirements: **Enabled**

![Password Policy](images/14-password-policy.png)

---

### **1️⃣5️⃣ Domain Login Verification**
After applying GPOs and restarting, verify login using domain credentials:
> `JCB\Administrator` or a domain user

![Final login](images/15-final-login.png)

---

## 🧩 Skills Demonstrated

- Windows Server deployment and configuration  
- Active Directory domain design and role installation  
- DNS name resolution and static addressing  
- Organizational Unit and user management  
- Group Policy implementation and enforcement  
- Troubleshooting domain controller warnings and delegation issues  

---

## 🔗 Related Lab Project

**[OPNsense Multi-Network Lab (Firewall & Routing)](https://github.com/Dmatthew227/opsense-multinet-lab)**  
A multi-subnet network lab using OPNsense, demonstrating routing, DHCP, and VLAN segmentation across virtual networks.

---

## 🧰 Tools Used

| **Tool** | **Purpose** |
|-----------|--------------|
| VMware Workstation / VirtualBox | Virtual environment for Server 2019 |
| Windows Server 2019 ISO | Operating System |
| Server Manager | Role management |
| ADUC / GPMC | User, OU, and policy configuration |
| PowerShell | Verification, administration tasks |

---

## 🏁 Final Thoughts

This lab provides a foundational understanding of how **Active Directory environments** are structured and managed in real-world networks.  
It mirrors tasks a **junior system administrator** or **network technician** would perform daily — such as configuring static IPs, creating OUs, managing users, and enforcing domain-wide security through Group Policy.

---

## 📜 License
MIT — free to use and adapt for educational or professional purposes.
