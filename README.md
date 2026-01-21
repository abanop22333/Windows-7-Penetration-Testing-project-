# 💣 Windows 7 EternalBlue – Penetration Testing Lab

![License](https://img.shields.io/badge/License-MIT-green.svg)
![Category](https://img.shields.io/badge/Category-Cybersecurity-red.svg)
![Tool](https://img.shields.io/badge/Tool-Metasploit-blue.svg)
![Target](https://img.shields.io/badge/Target-Windows%207-blue.svg)

> **BobXploit Brand 🛡️💻**
> A hands-on penetration testing project demonstrating the exploitation of the critical **MS17-010 (EternalBlue)** vulnerability in a controlled educational environment.

---

## 🚀 Project Overview

This lab demonstrates the end-to-end attack lifecycle against a vulnerable Windows 7 machine. The primary goal is to illustrate how an unpatched SMBv1 protocol can lead to a full system compromise, providing high-level administrative access (SYSTEM).

### 🎯 Key Features
* **Reconnaissance:** Advanced SMB service enumeration.
* **Vulnerability Detection:** Precision scanning for MS17-010.
* **Exploitation:** Reliable Remote Code Execution (RCE) via Metasploit.
* **Privilege Escalation:** Automatic SYSTEM-level access.
* **Post-Exploitation:** NTLM hash extraction and credential cracking.
* **Documentation:** Fully mapped attack workflow for educational purposes.

---

## 🧰 Tech Stack & Tools

| Category | Tools Used |
| :--- | :--- |
| **Attacker OS** | Kali Linux 🐉 |
| **Scanning** | Nmap (Scripting Engine) |
| **Framework** | Metasploit Framework |
| **Payload** | Meterpreter (Reverse TCP) |
| **Cracking** | CrackStation / Hashcat |
| **Virtualization**| VMware / VirtualBox |

---

## 🧪 Lab Environment Setup

* **Target Machine:** Windows 7 (Vulnerable VM – "Blue")
* **Target IP:** `192.168.1.32`
* **Network Config:** Host-Only / NAT (Isolated Lab)
* **Access Level:** Root/SYSTEM achieved.

---

## 🛠️ Attack Walkthrough

### 1️⃣ Reconnaissance & Scanning
Initial phase to identify open ports and services running on the target.

```bash
# General service scan
nmap -sC -sV -p 445 192.168.1.32

# Full port discovery
nmap -p- -T4 192.168.1.32
