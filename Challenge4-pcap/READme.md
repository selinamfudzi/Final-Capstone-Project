## Challenge 4: Analyze a PCAP File to find information

# Step 1: Find and Analyze the SA.pcap File

Opened SA.pcap in Wireshark

<img width="1366" height="643" alt="image" src="https://github.com/user-attachments/assets/2ce307a6-a7c9-49a6-9e43-5154b61e645a" />

Analyze the content of the PCAP file to determine the IP address of the target computer and the URL location of the file with the Challenge 4 code

<img width="1615" height="790" alt="image" src="https://github.com/user-attachments/assets/336e0237-c678-400e-b1cb-3cdd5ed62cc2" />

Follow TCP streams to see paths revealed in the captured traffic.

<img width="960" height="504" alt="SA" src="https://github.com/user-attachments/assets/550a302a-b2b2-4047-ba93-19e867d36a44" />

# Step 2: Use a web browser to display the contents of the directories on the target computer.

Use a web browser to investigate the URLs listed in the Wireshark output. Find the file with the code for Challenge 4.

<img width="1366" height="643" alt="image" src="https://github.com/user-attachments/assets/a7344048-f907-4974-9af3-162a327d9231" />

<img width="1366" height="643" alt="image" src="https://github.com/user-attachments/assets/461d5b00-db91-416d-88bc-1325359b1854" />

What is the content of the file?
Answer:
username, password and signatures

What is the Challenge 4 code?
Answer:
21z-1478K

<img width="1366" height="643" alt="image" src="https://github.com/user-attachments/assets/d78fd7cf-dafc-4ca1-921e-ddae883d1603" />

# Step 3: Research and propose remediation that would prevent file content from being transmitted in clear text.

Two key remediation methods to prevent unauthorized viewing of file content are:

- Encrypting the file itself before sending it using tools like PGP/GPG, AES encryption, or BitLocker. The file remains encrypted until the intended recipient decrypts it, adding an extra layer of security even if the transmission channel is compromised.

- Implement IPsec or VPN tunneling: Use IPsec policies to encrypt all network traffic between clients and servers, or route SMB communications through a VPN, which creates an encrypted tunnel. 
