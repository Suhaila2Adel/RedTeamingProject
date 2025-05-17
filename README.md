# RedTeamingProject
Red Team Operations – Simulated Cyber Attack on "Morning Catch"
🔍 Overview
This project simulates a comprehensive red team engagement against a controlled environment provided by the fictional organization Morning Catch. The operation followed a full attack lifecycle inspired by the Cyber Kill Chain model, revealing multiple security vulnerabilities including weak credential practices, lack of network segmentation, vulnerable services, and poor log management.

The simulated adversarial engagement demonstrates real-world attack techniques including OSINT, phishing, reverse shell payload deployment, privilege escalation, persistent access establishment, and log obfuscation—executed ethically and within a scoped, pre-authorized testbed.

Methodology
The operation followed the Cyber Kill Chain methodology:

1. Reconnaissance
Passive: OSINT on employees, domains, technologies.

Active: Nmap scanning, SMTP/HTTP enumeration, directory brute-force, employee photo harvesting.

2. Weaponization
Created reverse shell payload using msfvenom.

Disguised as securityPatch.exe.

3. Delivery
Crafted phishing email via vulnerable SMTP.

Payload hosted via http.server.

4. Exploitation
Phishing email deceived CEO.

Execution of securityPatch.exe established reverse shell.

5. Installation (Persistence)
Created scheduled task (failed).

Achieved persistence via RDP, user creation, and crontab manipulation.

Applied chattr +i to prevent user removal or file modifications.

6. Obfuscation / Anti-forensics
Used shred to delete logs: /var/log/syslog, /var/log/auth.log, /var/log/xrdp.log.

📌 Key Findings
Issue	Description
🔓 Vulnerable Services	Outdated Sendmail 8.14.3
🔑 Weak Credentials	Exposed employee directory with default credentials
🔀 No Network Segmentation	Enabled lateral movement
🎣 Social Engineering	CEO successfully phished
📂 Insecure Web Directories	Exposed user photos publicly
🧱 Weak Persistence Controls	Achieved root access with resilient persistence
🚫 Poor Logging Practices	Logs were deleted without detection

✅ Recommendations
🔴 Critical
Monitor and restrict cron/schtasks

Lock down scheduled tasks creation

🟠 High
Centralize logs and monitor deletions

Deploy File Integrity Monitoring (FIM)

Audit sudoers and restrict root delegation

🟡 Medium
Monitor access to sensitive files like /etc/passwd and /etc/shadow

🔵 Low
Disable directory listing and restrict web directories
