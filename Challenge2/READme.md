
## Challenge 2: Web Server Vulnerabilities

# Instructions
In this challenge, you must find vulnerabilities on an HTTP server. Misconfiguration of the web server allowed directory listing, which enabled the viewing of files and subdirectories through a web browser. Using reconnaissance techniques, you were required to locate the Challenge 2 flag file stored in a vulnerable directory.

## Step 1: Preliminary setup

a. Log into the server at 10.5.5.12 with the admin / password credentials.
    - Set the application security level to Low
    
<img width="1366" height="643" alt="image" src="https://github.com/user-attachments/assets/20885f75-c08b-4a61-9047-23112377c27f" />

<img width="1366" height="643" alt="image" src="https://github.com/user-attachments/assets/aa2f01e7-a531-452e-a0f6-6b77e4b83f84" />

## Step 2: From the results of your reconnaissance, determine which directories are viewable using a web browser and URL manipulation.

Perform reconnaissance on the server to find directories where indexing was found using Nikto Command: nikto -h 10.5.5.12

<img width="441" height="329" alt="Challenge 2" src="https://github.com/user-attachments/assets/c96ede3a-c9a1-4aec-a0fa-d81698e2b61c" />

-  Found the two viewable directories as **/config/** and **/docs/**

 <img width="1366" height="643" alt="image" src="https://github.com/user-attachments/assets/f9b4eddf-0368-4ec6-8b34-bb1da767e43a" />

## Step 3: View the files contained in each directory to find the db_form.html file.Create a URL in the web browser to access the viewable subdirectories. 

<img width="960" height="504" alt="SMB" src="https://github.com/user-attachments/assets/c8f9570a-4f8a-40aa-bf2c-75c6d995d654" />

In which two subdirectories can you look for the file?
➡️ Answer:
db_form.html
DVWA_v1.3.pdf

What is the filename with the Challenge 2 code?
➡️ Answer:
db_form.html

Which subdirectory held the file?
➡️ Answer:
/config/

What is the message contained in the flag file?
➡️ Answer:
aWe-4975

<img width="960" height="504" alt="smb 2" src="https://github.com/user-attachments/assets/76cb845a-796f-44b8-bfb6-7c185d4c645a" />

