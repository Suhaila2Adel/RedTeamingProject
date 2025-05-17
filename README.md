# Red Team Operations: Simulated Attack on "Morning Catch"

## Overview
Simulated adversarial engagement following the Cyber Kill Chain model against a fictional corporate environment. The operation revealed exploitable weaknesses using real-world attack techniques in a fully controlled and authorized testbed.

### Activities Included
- Passive and active reconnaissance
- Vulnerability enumeration
- Social engineering & phishing
- Payload delivery & execution
- Privilege escalation
- Persistence & obfuscation

- ## Tools & Technologies

- Kali Linux
- Nmap
- msfvenom
- Metasploit
- dirb
- Telnet
- RDP / rdesktop
- cron, schtasks
- chattr, shred


## 🛠️ Attack Chain Methodology

1. **Reconnaissance**  
   OSINT, Nmap, SMTP enumeration, employee data gathering

2. **Weaponization**  
   Payload generation using `msfvenom`

3. **Delivery**  
   Phishing via SMTP exploit, email spoofing

4. **Exploitation**  
   Payload executed by CEO, reverse shell established

5. **Installation**  
   Persistence via RDP, crontab, user creation, `chattr +i`

6. **Obfuscation / Anti-forensics**  
   `shred` used to destroy logs and hide traces


## Key Findings

- Unpatched Sendmail (8.14.3) vulnerability
- Weak credential practices and public user directories
- Susceptibility to phishing (CEO compromised)
- Lack of network segmentation
- Poor log monitoring (shred not detected)
- Resilient persistence mechanisms using cron and file immutability


## ✅ Security Recommendations

### 🔴 Critical
- Monitor and restrict cron/schtasks creation
- Enforce strict scheduled task permissions

### 🟠 High
- Centralize and protect logs
- Use File Integrity Monitoring (FIM)
- Audit sudoers configuration

### 🟡 Medium
- Monitor access to sensitive system files

### 🔵 Low
- Disable directory listing on web server
