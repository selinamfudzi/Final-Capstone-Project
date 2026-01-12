
## Challenge 3: Exploit open SMB Server Shares

In this part, you want to discover if there are any unsecured shared directories located on an SMB server in the 10.5.5.0/24 network. You can use any of the tools you learned in earlier labs to find the drive shares available on the servers.

# Step 1:Scan for potential targets running SMB.

- Scanned the 10.5.5.0/24 network with nmap command 'nmap 10.5.5.0/24' for hosts with open ports associated with SMB services and found the host 10.5.5.14 with ports 139 and 445 open. These ports are associated with SMB services.

  <img width="317" height="121" alt="server shares" src="https://github.com/user-attachments/assets/d2d81ac1-d3cf-4d2f-9b53-9d5782f5214f" />

### Scan for Potential Targets Running SMB

Use a scanning tool like nmap to identify hosts on the 10.5.5.0/24 network with open SMB-related ports (typically 139 for NetBIOS and 445 for Microsoft-DS/SMB).

- Command:
  
   nmap -p139,445 10.5.5.0/24 
    
