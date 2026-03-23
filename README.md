# mr-robot-ctf-penetration-test-thm
A comprehensive, end‑to‑end penetration testing project based on the Mr. Robot CTF from TryHackMe. This repository documents the full assessment lifecycle, including reconnaissance, enumeration, exploitation, reverse shell acquisition, privilege escalation, and remediation recommendations.Includes methodology, findings, risk analysis, and evidence aligned with industry‑standard penetration testing practices.

Mr. Robot CTF – Penetration Testing Report  
Author: Adeseye Nelson Olaiyapo  
Platform: TryHackMe  
Assessment Type: Black‑Box Penetration Test  
Overall Risk Rating: HIGH  


 Overview
This repository contains a full penetration testing assessment performed against the Mr. Robot CTF hosted on TryHackMe. The objective of this engagement was to simulate a real‑world attack scenario, identify vulnerabilities, exploit weaknesses, and demonstrate complete system compromise from an external attacker’s perspective.

The assessment follows industry‑standard methodologies and includes detailed evidence, exploitation steps, and remediation guidance.

 Scope of Assessment
 Target: Mr. Robot CTF (TryHackMe Room)  
 Testing Style: Black‑Box  
 Focus Areas:
 Web Application Enumeration  
 Service Enumeration  
 Credential Attacks  
 Reverse Shell Acquisition  
 Privilege Escalation  
 Root Compromise  

Methodology

 1. Information Gathering
- Identified target IP from TryHackMe instance  
- Performed host discovery and connectivity checks  
- Collected HTTP banners and initial responses  

2. Service Enumeration
 Conducted port scanning using `rustscan` and `nmap`  
 Enumerated WordPress components using `wpscan`, `curl`, and `wget`
 Discovered hidden directories such as `/robots.txt` and `/fsociety.dic`  
“Directory brute forcing revealed hidden paths such as /robots.txt and /fsociety.dic.”

 3. Vulnerability Identification
- Identified exposed sensitive files  
- Extracted credentials and hashes  
- Mapped attack paths including weak authentication and command execution vectors  

4. Exploitation
 Used WordPress weaknesses to gain initial foothold  
 Retrieved flags and sensitive files  
 Executed commands on the target system  

5. Reverse Shell
 Uploaded/modified theme file (`404.php`) to trigger remote command execution
 Received interactive shell via Netcat  
“This screenshot shows the attacker receiving a reverse shell from the Mr. Robot target machine.” 

 6. Privilege Escalation
 Enumerated SUID binaries and misconfigurations  
 Identified vulnerable `/usr/local/bin/nmap` SUID binary  
 Used GTFOBins technique to escalate to root  
“/usr/local/bin/nmap was discovered… used to gain root access.”






 Key Findings


No	| Finding |	Risk | Level |	Summary
1.	| Insecure Web Application Exposure |	High |	 Sensitive files exposed, enabling further compromise
2.	| Weak / Reused Credentials |	Medium |	Wordlist and base64 hash allowed credential cracking
3.	| Remote Code Execution (Reverse Shell) | 	 High | 	 Arbitrary command execution via WordPress theme(twenty fifteen)
4.	| Privilege Escalation to Root | 	 Critical |	 SUID misconfiguration allowed full system takeover


 Impact Summary
If these vulnerabilities existed in a production environment, an attacker could:

 Gain unauthorized access to sensitive data  
 Execute arbitrary commands  
 Obtain a persistent reverse shell  
 Escalate privileges to root
 Fully compromise confidentiality, integrity, and availability  

Remediation Recommendations

Web Application Hardening
 Restrict access to sensitive directories  
 Remove unnecessary files from web root  
 Update WordPress, themes, and plugins  

Credential Security
 Enforce strong, unique passwords  
 Avoid storing credentials in plaintext  
 Enable MFA for admin interfaces  

Server Hardening
 Remove unnecessary SUID binaries  
 Apply least‑privilege principles  
 Patch outdated components  

Network & Monitoring
 Implement outbound traffic restrictions  
 Enable detailed logging and monitoring  
 Perform regular vulnerability assessments  

 Repository Contents

 `/report/` – Full penetration testing report  
 `/evidence/` – Screenshots and proof‑of‑concept outputs  
 `/scripts/` – Commands and automation used during exploitation  
 `/notes/` – Enumeration notes and methodology references 
 
Conclusion
The Mr. Robot CTF demonstrates how a chain of weaknesses—exposed files, weak credentials, remote code execution, and privilege escalation—can lead to complete system compromise. Addressing these issues significantly improves the security posture of any similar environment.

 Contact
For questions or collaboration:  www.linkedin.com/in/adeseyeolaiyapo
Adeseye Nelson Olaiyapo


