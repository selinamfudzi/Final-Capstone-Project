# Final-Capstone-Project

* Overview

This repository documents a complete penetration testing engagement conducted as part of a final capstone Capture The Flag (CTF) exercise. The goal was to identify vulnerabilities, exploit them ethically, locate flag files, and propose remediation steps.

The assessment followed a real-world ethical hacking workflow, starting from reconnaissance and ending with reporting and recommendations.

 Objectives

Perform a full penetration test using ethical hacking techniques

Identify and exploit vulnerabilities to locate flag files

Analyze network traffic for sensitive information

Document findings and propose remediation strategies

 Scope

Engagement Type: Black-box penetration testing (simulated environment)

Target: Vulnerable systems provided for educational purposes

Authorization: Explicitly permitted (CTF simulation)

Tools Used

Nmap

OWASP ZAP 

Web browser

SQL injection techniques

Enum4Linux

smbclient

Wireshark

Methodology

Reconnaissance & Scanning

Vulnerability Identification

Exploitation

Flag Discovery

Scope & Objectives
Perform SQL Injection attacks to retrieve sensitive credentials
Exploit web server misconfigurations
Enumerate and exploit open SMB shares
Analyze packet captures (PCAP) for sensitive data exposure
Propose mitigation and remediation strategies
Target networks:

10.5.5.0/24
192.168.0.0/24
Challenges Completed
Challenge 1: SQL Injection
Identified vulnerable input fields
Extracted database credentials using SQL Injection
Cracked password hashes
Accessed a protected system using compromised credentials
Retrieved the flag file
Key Skills: SQLi, password cracking, web exploitation

Challenge 2: Web Server Vulnerabilities
Conducted directory enumeration
Identified directory listing misconfigurations
Navigated exposed subdirectories
Retrieved flag file via URL manipulation
Key Skills: Web reconnaissance, directory enumeration

Challenge 3: SMB Share Exploitation
Scanned the network for SMB services
Enumerated anonymous shares
Accessed unsecured SMB directories
Downloaded and analyzed flag files
Key Skills: SMB enumeration, lateral access

Challenge 4: PCAP Analysis
Analyzed captured network traffic using Wireshark
Identified sensitive data transmitted in clear text
Extracted URLs, IP addresses, and exposed file contents
Retrieved final challenge flag
Key Skills: Network traffic analysis, data exposure detection

Tools Used
Kali Linux
DVWA
Nmap
smbclient
Wireshark
Web Browser Developer Tools
Remediation Summary
Each challenge includes remediation guidance covering:

Input validation and prepared statements
Secure web server configuration
SMB access control and hardening
Encryption of data in transit (HTTPS, SMB signing)


Remediation Recommendations


Summary of Findings
Challenge	Vulnerability Type	Risk Level
1	SQL Injection	High
2	Directory Enumeration	Medium
3	SMB Misconfiguration	High
4	Plaintext Network Traffic	Medium

 Lessons Learned

Reconnaissance is critical to discovering attack paths

Minor misconfigurations can lead to major security breaches

Manual analysis is essential alongside automated tools

Persistence and trial-and-error are part of real penetration testing

 Conclusion

This capstone exercise provided hands-on experience with real-world penetration testing techniques. It reinforced secure configuration principles, vulnerability analysis, and ethical exploitation while emphasizing the importance of documentation and remediation.

⚠️ Disclaimer

This project was conducted in a controlled, educational environment. All techniques demonstrated were used with authorization and strictly for learning purposes.
