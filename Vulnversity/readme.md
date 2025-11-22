# TryHackMe — Vulnversity Walkthrough

This README contains my full walkthrough summary for the **Vulnversity** room on TryHackMe.  
The room covers core penetration-testing skills such as enumeration, scanning, exploitation, and privilege escalation.

---

## 🔍 1. Enumeration

### **Nmap Scan**

Performed a full port and service scan to map the attack surface:

- Discovered open ports including HTTP and SSH
- Used service/version detection for more detail
- Identified potential attack vectors through exposed services

---

## 🌐 2. Web Enumeration

### **Gobuster / Directory Busting**

- Enumerated hidden directories on the web server
- Found an upload functionality which became the key entry point

### **Manual Testing**

- Tested the upload form
- Observed file type restrictions
- Confirmed that upload validation could be bypassed

---

## 📤 3. File Upload Exploitation

Bypassing filters, I:

- Uploaded a reverse-shell payload disguised as a valid file
- Triggered the payload to gain execution on the target machine

---

## 💻 4. Initial Shell Access

Once the shell connected:

- Stabilized the terminal
- Checked system info and user privileges
- Explored directories for potential privesc vectors

---

## ⬆️ 5. Privilege Escalation

### **SUID Enumeration**

Executed:
find / -user root -perm -4000 -exec ls -ldb {} ; 2>/dev/null

Found a SUID-enabled binary that could be abused to escalate privileges.

Used it to:

- Execute privileged commands
- Gain a **root shell**

---

## 🧾 6. Flag Collection

Captured:

- **User flag**
- **Root flag**

Both were located in their respective home directories.

---

## ✨ Skills Practiced

- Nmap scanning
- Directory & file enumeration
- Upload bypass techniques
- Reverse shells
- Linux privilege escalation
- SUID exploitation
- Documentation & reporting

---

## 🎯 Room

TryHackMe — **Vulnversity**

---

## 📌 Notes

This content is for educational and portfolio purposes only.  
All testing was done in TryHackMe's legal environment.
