# RedTeamingProject
This red team operation successfully simulated a targeted cyberattack against 
the Morning Catch environment. The engagement highlighted critical security 
gaps, including unpatched legacy systems, weak credential practices, and lack 
of network segmentation. 
The operation began with passive and active reconnaissance, where we 
identified exposed services and extracted valid usernames via SMTP 
enumeration. Using this information, a reverse shell payload was crafted with 
msfvenom and disguised as a legitimate system update. The payload was 
delivered through a phishing email composed and sent via a vulnerable SMTP 
service, 
exploiting social engineering techniques to lure the CEO into executing the 
malicious file. 
Upon execution, the payload established a reverse shell to the attacker’s 
machine, enabling full control of the target. Persistence was achieved using a 
scheduled task that ensured recurring execution of the payload. Command and control were maintained via RDP using valid credentials, followed by privilege 
escalation to root access. This allowed for full administrative control and set 
the stage for lateral movement toward a second target within the defined test 
scope. 
The engagement successfully demonstrated how a motivated attacker could 
chain together multiple attack vectors—information gathering, phishing, 
payload execution, persistence. These findings underscore the need for 
improved system hardening, user awareness training, and proactive detection 
capabilities.
