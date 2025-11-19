# 🐉 Hydra – TryHackMe Room (My Work)

This README contains **all my work, notes, commands, and understanding** from the Hydra room on TryHackMe.  
I solved the room and documented everything here for learning purposes.

---

## 🔥 Overview
Hydra is a fast password-bruteforce tool used to attack different login services like:
- SSH  
- FTP  
- HTTP login forms  
- Many more

---

## 🧠 What I Learned
- How brute-force attacks actually work  
- How to identify login parameters  
- How to use wordlists correctly  
- How to target SSH, FTP & HTTP forms  
- Understanding responses (success/failure strings)

---

## 🛠️ Commands I Used

### SSH attack
```bash
hydra -l USERNAME -P wordlist.txt ssh://TARGET_IP
### HTTP POST Form attack
hydra -l admin -P passwords.txt TARGET_IP http-post-form "/login:username=^USER^&passwo