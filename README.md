# 🔐 OpenVPN Host-to-Network VPN with 2FA

## 📌 Project Overview
This project demonstrates the configuration of a **secure host-to-network VPN** using **OpenVPN on pfSense** with **FreeRADIUS authentication** and **Two-Factor Authentication (2FA)** via Google Authenticator (TOTP).  

The deployment simulates a real-world enterprise environment where remote users securely connect to internal resources with **encrypted tunnels** and **multi-factor authentication**.  

---

## ⚙️ Tools & Environment
- **Firewall/Router:** pfSense 2.7.2  
- **Authentication:** FreeRADIUS (via pfSense package manager)  
- **VPN Protocol:** OpenVPN (UDP 1194, AES-256-GCM encryption)  
- **2FA:** Google Authenticator (TOTP)  
- **Virtualization:** VMware vSphere  
- **Client:** Windows 10 (OpenVPN GUI)  

---

## 🚀 Key Features
- Host-to-Network (Road Warrior) VPN setup on pfSense  
- Centralized authentication with **FreeRADIUS**  
- TOTP-based **2FA** using Google Authenticator  
- Secure **certificate-based encryption** (AES-256-GCM)  
- Configured **firewall rules** to allow VPN traffic  
- Tested connectivity with **ping, tracert, and OpenVPN logs**  

---

## 🛠️ Configuration Steps (Summary)
1. Installed **FreeRADIUS** and OpenVPN Client Export utility on pfSense.  
2. Configured **RADIUS clients, users, and OTP secrets**.  
3. Integrated **Google Authenticator** for TOTP 2FA.  
4. Created **Certificate Authority (CA)** and server certificates.  
5. Configured **OpenVPN server** with FreeRADIUS backend.  
6. Added **firewall rules** for UDP 1194 and OpenVPN tunnel traffic.  
7. Exported and imported **client configuration** into OpenVPN GUI.  
8. Successfully authenticated with **username, password, and TOTP code**.  

---

## 🧪 Testing & Results
- ✅ VPN client successfully assigned a **virtual IP** (10.0.241.6).  
- ✅ Authentication required **username + password + TOTP code**.  
- ✅ Ping and traceroute confirmed secure tunnel routing.  
- ✅ pfSense OpenVPN status showed **active sessions**.  

---

## ⚠️ Challenges & Solutions
- **TOTP sync issue** → Fixed by enabling **NTP time sync** on pfSense.  
- **Port mismatch** (RADIUS 1812/1813) → Corrected in FreeRADIUS and pfSense settings.  
- **Firewall blocking traffic** → Added rules on both **WAN** and **OpenVPN tabs**.  

---

## 📚 Lessons Learned
- Accurate **time synchronization** is critical for TOTP-based 2FA.  
- **Firewall rules** can block traffic even when tunnels are established.  
- Centralized RADIUS authentication scales better than local users.  
- Debugging with **logs, ping, and traceroute** is essential for VPN troubleshooting.  

---

## 📷 Screenshots

![FreeRADIUS Users](images/freeradius-users.png)  
*Figure 1: FreeRADIUS user configuration with OTP enabled*

![VPN Login with TOTP](images/vpn-login.png)  
*Figure 2: OpenVPN login requiring username, password, and TOTP code*

![VPN Connection Successful](images/vpn-connected.png)  
*Figure 3: Successful VPN connection status in pfSense*

![Ping Test](images/ping-test.png)  
*Figure 4: Tunnel connectivity confirmed with ping*

 

---

## 📑 Full Report
The complete project documentation, including step-by-step configuration and detailed figures, is available in the [Project Report](docs/OpenVPN_Project_Report.pdf).  

---

## 🏆 Key Takeaway
This project highlights how combining **pfSense, FreeRADIUS, and TOTP-based 2FA** creates an enterprise-ready, secure, and scalable VPN infrastructure. It demonstrates strong hands-on skills in **network security, authentication, and troubleshooting**, aligning with industry best practices.  

---

## 📖 References
- National Institute of Standards and Technology (NIST). (2020). *Digital Identity Guidelines – SP 800-63-3.* https://pages.nist.gov/800-63-3/  
- Netgate. (2024). *pfSense Documentation.* https://docs.netgate.com/pfsense/en/latest/  
- OpenVPN. (2023). *Community Wiki.* https://community.openvpn.net  

---
