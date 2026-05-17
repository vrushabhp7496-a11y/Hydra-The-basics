### Hydra :
- Hydra is the password cracking tool.
- This tool is password list based.
- when we provide password list and username list this will try each and evry password combination to crack it.
- If you are using weak password this shows importance of using strong password and MFA.

---

### Below i entioned all necessary flags related to hydra :

---

| Situation | Hydra Flag | Example |
|-----------|------------|---------|
| Username is known | `-l` (small L) | `hydra -l admin -P pass.txt ssh://target` |
| Username not known | `-L` (capital L) | `hydra -L users.txt -P pass.txt ssh://target` |
| Single Password – Username Guess | `-p` (small p) | `hydra -L users.txt -p password123 ssh://target` |
| Password Wordlist – Username Guess | `-P` (capital P) | `hydra -L users.txt -P pass.txt ssh://target` |
