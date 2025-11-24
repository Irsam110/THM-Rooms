# TryHackMe: Metasploit Introduction — Writeup

This repository contains my writeup for the **Metasploit Introduction** room on TryHackMe.  
The room focuses on learning the basics of the **Metasploit Framework**, identifying modules, using exploits, auxiliary scanners, payloads, and interacting with sessions.

---

## Overview

- Room: Metasploit Introduction
- Difficulty: Easy
- Category: Metasploit / Enumeration / Exploitation
- Focus Areas:
  - Understanding Metasploit modules
  - Searching and selecting exploits
  - Using auxiliary scanners
  - Setting payloads and options
  - Running exploits and interacting with sessions

---

## What I Learned

- How Metasploit is organized (Exploit, Auxiliary, Post, Payload, Encoders)
- How to search for modules using keywords
- How to inspect and configure module options
- Running auxiliary scanners for information gathering
- Launching exploits against a target
- Opening and interacting with Meterpreter sessions

---

## Module Searching

Example of searching for a relevant exploit:

```bash
search samba
This lists related exploits, auxiliary scanners, and payloads.
2. Using a module
use <module-path>


Example:

use auxiliary/scanner/smb/smb_version


This loads the module into the console.

3. Checking module options
show options


This displays:

Required settings

Network parameters

Payload options (if any)

Example output shows fields like:

RHOSTS – target

RPORT – port

THREADS – speed

4. Setting options
set RHOSTS <TARGET-IP>
set RPORT 445

5. Running the module
run


or

exploit

6. Handling sessions

When an exploit succeeds, Metasploit creates a session.

List all sessions:

sessions -l


Interact with one session:

sessions -i 1


Inside Meterpreter, I used commands like:

sysinfo
getuid
ls
cd C:\

What I Learned in This Room

How to search for exploits, auxiliary modules, and payloads

How to load modules with use

How to inspect options using show options

How to configure the module settings properly

How to execute a module

How Meterpreter sessions work

Navigating inside a compromised system

Conclusion

The Metasploit Introduction room helped me understand the core structure of Metasploit and how to use its essential commands.
By practicing module searching, configuration, execution, and session management, I built a strong foundation for future exploitation and post‑exploitation rooms on TryHackMe.
```
