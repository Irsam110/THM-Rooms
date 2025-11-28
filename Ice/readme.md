# TryHackMe ICE Room - Learning Journey

## Overview

I recently completed the **TryHackMe "ICE" room**, which focused on Windows post-exploitation, privilege escalation, and reconnaissance techniques. This room provided a hands-on environment to practice real-world penetration testing skills using **Metasploit, Meterpreter, and various post-exploitation modules**.

Through this room, I explored techniques that attackers often use to gain persistence, escalate privileges, and interact with compromised systems while also understanding how defenders can detect such actions.

---

## Key Learnings

### 1. Meterpreter Fundamentals

- **Session management**: Interacting with compromised machines and maintaining control.
- **Process migration**: Moving Meterpreter sessions into more stable/system processes (`spoolsv.exe`, `explorer.exe`) to maintain stealth and gain additional privileges.
- **User and SYSTEM privileges**: Understanding how privileges affect what actions can be performed on a target.

### 2. Post-Exploitation Modules

- **`post/multi/recon/local_exploit_suggester`**: Identified potential local exploits based on the target machine.
- **UAC bypass**: Explored bypass techniques (`bypassuac_eventvwr`) to gain higher privileges on the system.

### 3. Credential Access

- **Mimikatz / Kiwi**:
  - Extracted credentials and hashes from memory.
  - Learned about **Golden Ticket attacks** to maintain access in a domain environment.
  - Understood **Kerberos TGT and domain authentication** and how attackers abuse it for persistence.

### 4. Persistence Techniques

- **Metasploit persistence script** (`run persistence`):
  - Enabled Meterpreter to automatically reconnect after system restart.
- **Scheduled Tasks & Registry run keys**:
  - Learned how attackers establish stealthy and durable access to a compromised system.

### 5. Remote Interaction

- **Screenshare (`screenshare`)**: Observed the target user’s desktop in real-time.
- **Microphone recording (`record_mic`)**: Captured audio from the target machine when permissions allowed.
- **Remote Desktop (RDP)**: Enabled RDP on target machines using `run post/windows/manage/enable_rdp` to log in as a real user.

### 6. Anti-Forensics Awareness

- **Timestomp**: Explored how file timestamps can be modified to confuse forensic investigators.
- Emphasized that these techniques should only be practiced in **authorized labs**.

---

## Tools & Modules Practiced

- **Metasploit Framework**
- **Meterpreter**
- **Kiwi (Meterpreter Mimikatz extension)**
- `ps`, `migrate`, `hashdump`, `getuid`, `sysinfo`
- Post-exploitation modules:
  - `post/multi/manage/enable_rdp`
  - `post/windows/manage/persistence`
  - `post/multi/recon/local_exploit_suggester`
- Commands:
  - `screenshare`, `record_mic`, `timestomp`
  - `golden_ticket_create` (domain lab scenario)

---

## Reflection

This room strengthened my understanding of:

- Realistic Windows post-exploitation workflows.
- How privilege escalation works and why process migration is crucial.
- Credential extraction, Golden Ticket attacks, and persistence strategies.
- Ethical considerations in pentesting and anti-forensics techniques.

Completing this room improved my practical skills and prepared me for **real-world penetration testing scenarios**, emphasizing both **attacker techniques** and **defender awareness**.

---

## Disclaimer

All exercises were performed in a **legal, lab-controlled environment (TryHackMe)**. Techniques discussed should **never be used on unauthorized systems**.

---
