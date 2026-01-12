
## Challenge 3: Exploit open SMB Server Shares

In this part, you want to discover if there are any unsecured shared directories located on an SMB server in the 10.5.5.0/24 network. You can use any of the tools you learned in earlier labs to find the drive shares available on the servers.

# Step 1:Scan for potential targets running SMB.

- Scanned the 10.5.5.0/24 network with nmap command 'nmap 10.5.5.0/24' for hosts with open ports associated with SMB services and found the host 10.5.5.14 with ports 139 and 445 open. These ports are associated with SMB services.

### Scan for Potential Targets Running SMB

Use a scanning tool like nmap to identify hosts on the 10.5.5.0/24 network with open SMB-related ports (typically 139 for NetBIOS and 445 for Microsoft-DS/SMB).

- Command:
  
   nmap -p139,445 10.5.5.0/24 
    
 <img width="317" height="121" alt="server shares" src="https://github.com/user-attachments/assets/d2d81ac1-d3cf-4d2f-9b53-9d5782f5214f" />

# Step 2:Determine which SMB directories are shared and can be accessed by anonymous users.

Enumerated SMB shares on the identified host using enum4linux with the command enum4linux -S 10.5.5.14

<img width="1366" height="643" alt="image" src="https://github.com/user-attachments/assets/f3f27581-6fe9-4545-9105-b3cc4519e442" />

<img width="345" height="504" alt="shares 1" src="https://github.com/user-attachments/assets/08d701a1-8490-49f9-bd51-888fba7b139c" />

Determined which shares could be accessed without valid user credentials using the commad smbmap -H 10.5.5.14

<img width="1366" height="643" alt="image" src="https://github.com/user-attachments/assets/d612f921-1804-4d62-90a4-a38691576fde" />

<img width="357" height="457" alt="smbclient other" src="https://github.com/user-attachments/assets/deb2ce2b-1b0e-4f38-835f-6c6b049dd5b4" />

What shares are listed on the SMB server? Which ones are accessible without a valid user login?
 Answer:
homes workfiles print$ IPC$

# Step 3: Locate and Retrieve the Challenge 3 File
Accessed the SMB server using an SMB client
Navigated through shared directories to locate the file containing the Challenge 3 code
Downloaded and opened the file locally

<img width="357" height="241" alt="smb client 1" src="https://github.com/user-attachments/assets/076f6411-c5cd-4975-b756-5d3e0c6f3492" />

<img width="1366" height="643" alt="image" src="https://github.com/user-attachments/assets/9a27268c-df6d-4c28-a3b6-4e40a983ac3a" />

# Step 4: Research and Propose SMB Attack Remediation

What are two remediation methods for preventing SMB servers from being accessed?
These are;

- Network segmentation and firewall rules to restrict access to trusted IPs/VLANs

- Disabling legacy SMB versions (SMBv1) and enforcing strong authentication (like Kerberos/NTLMv2 with MFA) to prevent exploits and interception.

