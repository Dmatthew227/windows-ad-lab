
---

## 🗺️ Steps & Screenshots

### 1) Install Windows Server
Basic OS installation from ISO.

![Installing Windows](images/01-installing-windows.png)

### 2) Set the local Administrator password
  
![Admin password](images/02-admin-password.png)

### 3) First login
Use **Ctrl+Alt+Delete** → sign in as **Administrator**.

![First login](images/03-first-login.png)

### 4) Open Server Manager
We’ll use **Server Manager** to configure roles and features.

![Server Manager](images/04-server-manager.png)

### 5) Configure static IPv4
Assign a static IP address and set DNS to point to itself (loopback or same IP).

![Static IP config](images/05-static-ip-config.png)

### 6) Rename the server
Set a meaningful hostname before promoting to DC.

![Server name](images/06-server-name.png)

### 7) Add Roles: AD DS + DNS
Through **Add roles and features**, install both roles.

![Installing AD DS](images/07-installing-ad-ds.png)

### 8) Roles installed successfully
AD DS role and management tools now available.

![AD DS installed](images/08-ad-ds-installed.png)

### 9) DNS configuration options
Review DNS delegation warning — expected in a standalone lab.

![DNS options](images/09-dns-options.png)

### 10) DNS warnings
Normal for single DC environments.

![DNS warnings](images/10-dns-warnings.png)

### 11) Create OUs & Users
After promotion and reboot, open **Active Directory Users and Computers** to create OUs and users.

![Users and Groups](images/11-users-and-groups.png)

### 12) Verify Server Roles
Confirm **AD DS** and **DNS** are healthy in **Server Manager**.

![Dashboard](images/12-dashboard.png)

### 13) Create a Group Policy Object (GPO)
Open **Group Policy Management** and create a new GPO called “Password Policy”.

![Create GPO](images/13-create-gpo.png)

### 14) Configure password policy
Enable complexity, set minimum length, and enforce password history.

![Password Policy](images/14-password-policy.png)

### 15) Final domain login
Log in using **DOMAIN\Administrator** or a created domain user.

![Final login](images/15-final-login.png)

---

## ✅ What I Practiced

- Installing and configuring **Windows Server 2019**
- Deploying **Active Directory Domain Services** and **DNS**
- Promoting a standalone server to **Domain Controller**
- Structuring **Organizational Units** and managing users
- Applying **Group Policy** for password and security policies

---

## 🔗 Related Project

**[OPNsense Multi-Network Lab (Firewall & Routing)](https://github.com/Dmatthew227/opsense-multinet-lab)**  
Demonstrates multi-network routing, DHCP, and firewall policies using OPNsense.

---

## 📄 License
MIT — see [LICENSE](LICENSE)
