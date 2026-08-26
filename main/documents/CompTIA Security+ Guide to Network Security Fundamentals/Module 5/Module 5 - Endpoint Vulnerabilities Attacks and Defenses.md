---
created: 2026-08-20 10:00:00
class:
  - document
description: CompTIA Security+ SY0-701 Module 5 — malware attacks, application vulnerabilities, and securing endpoint devices
mod.: 2026-08-20 10:00:00
aliases:
  - security+ module 5
  - endpoint vulnerabilities attacks and defenses
tags:
  - study/security-plus
  - study/security-plus/module-5
---

# Module 5 - Endpoint Vulnerabilities, Attacks, and Defenses

## Objectives

1. [[#Objective 1 - Malware Attacks|Identify the different types of attacks using malware]]
2. [[#Objective 2 - Application Vulnerabilities and Attacks|Describe attacks based on application vulnerabilities]]
3. [[#Objective 3 - Securing Endpoint Devices|Explain the steps of securing endpoint devices]]

---

## Objective 1 - Malware Attacks

### What Is Malware?
- **Malware** (malicious software): software designed to interfere with a computer's normal functions and can be used to commit an unwanted and harmful action
- Term coined in the early 1990s; estimated 560,000 new instances detected daily
- No standard classification exists; groupings based on primary action performed

#### Malware Actions (Groupings)

| Action | Description | Examples |
|--------|-------------|----------|
| **Kidnap** | Holds device hostage until ransom paid | Ransomware |
| **Eavesdrop** | Secretly listens to targets | Keyloggers, spyware |
| **Masquerade** | Pretends to be something else | Trojans, RATs |
| **Launch** | Infects computer to launch attacks on others | Viruses, worms, bloatware, bots |
| **Sidestep** | Evades detection | Logic bombs, rootkits, backdoors |

### Ransomware
- **Ransomware**: malicious software designed to extort money from victims in exchange for their endpoint device being restored to its normal working state
- Two general categories: blocking ransomware and locking ransomware

#### Blocking Ransomware
- Earliest form, widespread since ~2010
- Prevents user from using computer in normal fashion
- Manipulates OS to block normal access to device
- Displays fake message pretending to be from reputable third party (e.g., law enforcement claiming illegal activity, or software vendor claiming expired license)
- Payment and credit card number sent to threat actors

#### Locking Ransomware
- More malicious modern form
- Encrypts some or all files on the device so they cannot be opened
- Device remains functional so ransom can be easily paid
- Warning message with increasing urgency (cost rises, files deleted, deadline)
- New variants encrypt files on any connected network or storage device
- **Blended attacks**: steal data first, then lock files; threaten public release
- **Extortion**: threaten to sell stolen data to highest bidder

#### Why Ransomware Is the Most Serious Threat
- **Low barrier to entry**: ransomware can be rented for as little as $800/month
- **Pervasive attacks**: two out of three organizations experienced successful attack (2021); involved in one out of four data breaches
- **High impact**: 37% of companies forced to lay off employees, 35% reported senior manager resignations, 33% forced to temporarily suspend operations
- About 54% of organizations that paid the ransom reported system issues or corrupted data after decryption

### Keylogger
- **Keylogger**: silently captures and stores each keystroke a user types
- Attacker can search captured text for passwords, credit card numbers, personal information
- Can be a **software program** or a **small hardware device**

#### Software Keyloggers
- Programs installed on computer that silently capture sensitive information
- Go beyond keystrokes: screen captures, web camera activation
- Do not require physical access; can be installed remotely
- Routinely send captured information back to attacker via victim's own Internet connection

#### Hardware Keyloggers
- Small hardware devices inserted between keyboard connection and USB port
- Resemble ordinary keyboard connector; often on back of computer, go undetected
- Beyond reach of anti-malware scanning software
- **Disadvantage**: attacker must physically install and later remove device to access stored information

### Spyware
- **Spyware**: tracking software deployed without consent or control of user
- Secretly monitors users but makes no attempts to gather sensitive keyboard input (unlike keyloggers)
- Collects information without user approval using computer's resources

| Technology | Description | Impact |
|-----------|-------------|--------|
| **Automatic download software** | Downloads and installs software without user interaction | Could install unauthorized applications |
| **Passive tracking technologies** | Gathers information about user activities without installing software | Could collect private information such as websites visited |
| **System-modifying software** | Modifies user configurations (browser home page, search page, default media player) | Changes configurations to settings user did not approve |
| **Tracking software** | Monitors user behavior or gathers information about user | Could collect personal information that can be shared or stolen, resulting in fraud or identity theft |

### Trojan
- **Trojan**: executable program that masquerades as performing a benign activity but also does something malicious
- Named after the Trojan Horse of ancient legend
- Example: user downloads advertised calendar program that also installs malware to scan for credit card numbers and passwords

### Remote Access Trojan (RAT)
- **RAT**: special type of Trojan that gives threat agent unauthorized remote access to victim's computer
- Uses specially configured communication protocols
- Creates opening into victim's computer, allowing unrestricted access
- Attacker can: monitor user activity, change computer settings, browse and copy files, access other computers on the network

### Virus
- Two types: **file-based virus** and **fileless virus**

#### File-Based Virus
- Malicious computer code that becomes part of a file
- Similar to biological virus: attaches to host file, merges with its genes, tricks host into making copies
- **Appender infection**: virus attaches to end of file, inserts "jump" instruction at beginning pointing to virus code
- More advanced techniques: split infections, mutations, self-destructing when security tools detected
- Payload can: delete files, prevent programs from launching, steal data, cause crashes, turn off security settings
- Can only replicate on host computer; relies on user actions (email attachments, USB drives) to spread
- Over 50 different Windows file types can be infected (.docx, .xlsx, .exe, .msi, .ps1, etc.)

#### Fileless Virus
- Does not attach to a file; takes advantage of native OS services and processes to avoid detection
- Uses **LOLBins (living-off-the-land binaries)** — native services used in fileless virus
- Malicious code loaded directly into RAM through LOLBins and then executed
- Advantages: no specific file type needed, LOLBins have extensive control, can automatically launch, undetectable by anti-malware tools

| Windows LOLBin | Description |
|----------------|-------------|
| **PowerShell** | Cross-platform task automation and configuration management framework |
| **Windows Management Instrumentation (WMI)** | Microsoft standard for accessing management information about devices |
| **.NET Framework** | Cross-platform developer platform for building applications |
| **Macro** | Series of instructions grouped as single command; stored within user documents (Excel .xlsx, Word .docx) |

### Worm
- **Worm**: malicious program that uses a computer network to replicate (sometimes called "network virus")
- Designed to enter computer through network, exploit vulnerability, then immediately search for another vulnerable computer on network
- Early worms were benign, designed to spread quickly but not corrupt systems
- Today's worms can leave behind payload: delete files, allow remote control
- Key difference from viruses: viruses self-replicate on host computer; worms self-replicate between computers

### Bloatware
- **Bloatware**: software installed on a device without user requesting it
- Two categories: software preinstalled on new device; software installed due to overlooking default installation options
- Risks: could contain malware, could become platform for other malware to exploit
- Can inject advertising, display pop-ups, change default search engine/home page, add toolbars, redirect browsers

### Bot
- **Bot (zombie)**: infected computer placed under remote control of attacker for launching attacks
- Computer can act as bot while carrying out tasks of regular user (user unaware)
- **Botnet**: hundreds, thousands, or millions of bot computers gathered into logical network
- **Bot herder**: person controlling the botnet
- Commands received through **command and control (C&C)** structure
- Communication methods: bot-herding websites, third-party websites, blogs, social media posts

### Logic Bomb
- **Logic bomb**: computer code added to legitimate program that lies dormant until a specific logical event triggers it
- Once started, deletes data or performs other malicious activities
- Difficult to detect: embedded in very large programs; trusted employees can insert code without detection
- Many planted by disgruntled employees

### Rootkit
- **Rootkit**: malware that can hide its presence and presence of other malware on the device
- Accesses lower layers of OS or uses undocumented functions to make alterations
- Becomes undetectable by OS or anti-malware scanning software
- Risks significantly diminished today due to OS protections

### Backdoor
- **Backdoor**: gives access to computer, program, or service that circumvents normal security protections
- Allows attacker to return later and bypass security settings
- Legitimate backdoors created by developers for regular access; intended to be removed once application finalized
- Attackers use left-installed backdoors to bypass security

### Indicators of Attack (IoA)
- **Indicator of attack (IoA)**: sign that an attack is currently underway (different from indicator of compromise, which is evidence attack has already occurred)

| Indicator | Description |
|-----------|-------------|
| **Account lockout** | User account inaccessible through normal login attempt; may have been taken over by attacker |
| **Concurrent session usage** | Both legitimate user and attacker logged into same account |
| **Blocked content** | Data no longer accessible |
| **Impossible travel** | Accessing resource not possible due to geography (e.g., New York then Los Angeles five minutes later) |
| **Resource consumption** | System resources suddenly depleted |
| **Resource inaccessibility** | Large-scale attack blocking system resources |
| **Out-of-cycle logging** | Log records not corresponding to actual events |
| **Published/documented** | External sources evidence current attack |
| **Missing logs** | Log files mysteriously deleted |

---

## Objective 2 - Application Vulnerabilities and Attacks

### Privilege Escalation
- **Privilege escalation**: attacker gains illicit access of elevated rights or privileges beyond what is entitled
- **Horizontal**: gaining access to rights of another account with similar privileges
- **Vertical**: increasing the elevation of rights
- 44% of all Microsoft vulnerabilities resulted in vertical privilege escalation (in one year)

### Buffer Overflow
- **Buffer overflow attack**: process attempts to store data in RAM beyond boundaries of a fixed-length storage buffer
- Extra data overflows into adjacent memory locations
- Storage buffer typically contains "return address" — memory location of software program being executed when another function interrupted
- Attacker overflows buffer with new address pointing to their malware code
- Also called **injections** or **memory injections** — introduce something into RAM
- Often result of programmers not adhering to secure program development practices

### Improper Exception and Error Handling
- Application does not properly check for exceptions during execution
- Software that does not correctly "trap" error condition could provide attacker with underlying access to system
- Attacker enters unexpectedly long character string → program crashes → displays underlying OS prompt
- **NULL pointer/object dereference**: application dereferences pointer expected to be valid but has value NULL; causes crash
- Can result from **race condition**: two concurrent threads access shared resource simultaneously
- **TOC to TOU (time of check to time of use)**: software checks resource state before using it, but state changes between check and use
- Should be analyzed using **target of evaluation (TOE)** approach

### Directory Traversal
- "Root" directory on web server's file system; users restricted to root and subdirectories
- **Directory traversal attack**: exploits vulnerability so user can move from root directory to restricted directories, viewing confidential files or executing commands

### Cross-Site Scripting (XSS)
- **XSS attack**: website accepts user input without validating it ("sanitizing") and uses that input in a response
- Attacker tricks valid website into feeding malicious script to another user's browser
- Name refers to attack using scripting originating on one site to impact another site

### SQL Injection (SQLi)
- **SQLi**: inserts statements to manipulate a database server
- SQL (Structured Query Language): language used to view and manipulate data in relational database
- Attacker enters crafted SQL statements as user input to extract or manipulate database information
- Example: entering `' or 'a'='a` makes WHERE clause always true, displaying all records
- Can: determine field names, discover table names, find specific users, erase database tables, update records

### Request Forgery

| Attack | Target | Purpose |
|--------|--------|---------|
| **CSRF (Cross-Site Request Forgery)** | User | Force target to take action for attacker while pretending to be authorized user |
| **SSRF (Server-Side Request Forgery)** | Web server | Gain access to sensitive data or inject harmful data |

- **CSRF**: takes advantage of authentication token website sends to user's browser; new page inherits identity and privileges of victim; also called client-side request forgery
- **SSRF**: takes advantage of trusting relationship between web servers; attacker modifies target URL to extract sensitive information or inject untrusted input

### Replay Attack
- **Replay attack**: copies data and then uses it for an attack
- Commonly used against digital identities — intercepting, copying, and retransmitting edited portions of communications to impersonate legitimate user
- Often between user and authentication server

---

## Objective 3 - Securing Endpoint Devices

### Protecting Endpoints

#### Antivirus (AV) Software
- One of the first software protections for endpoint computers
- Examines computer for file-based virus infections, monitors activity, scans new documents
- If virus detected: clean file, quarantine infected file, or delete file
- Log files provide beneficial information regarding attacks

| Analysis Type | Method | Description |
|--------------|--------|-------------|
| **Signature-based (static analysis)** | String scanning, wildcard scanning, mismatch scanning | Attempts to match known virus patterns against potentially infected files |
| **Heuristic monitoring (dynamic analysis)** | Code emulation, behavioral characteristics | Spots characteristics of virus instead of attempting matches; creates virtual environment to simulate CPU/memory |

### Web Browsers

#### Secure Cookies
- **Cookie**: file where server stores user-specific information on user's local computer
- HTTP is stateless protocol; cookies help mimic stateful protocol

| Cookie Type | Description |
|-------------|-------------|
| **First-party cookie** | Created from website user is currently viewing |
| **Third-party cookie** | Additional cookies placed on local hard drive from third parties advertising on the site |
| **Session cookie** | Stored in RAM, lasts only for duration of visiting website |
| **Secure cookie** | Only sent to server with encrypted request over HTTPS; prevents interception |

#### HTTP Response Headers

| Header | Description | Protection |
|--------|-------------|------------|
| **HTTP Strict Transport Security (HSTS)** | Forces browser to communicate over HTTPS instead of HTTP | Encrypts transmissions |
| **Content Security Policy (CSP)** | Restricts resources user is allowed to load within website | Protects against injection attacks |
| **Cross Site Scripting Protection (X-XSS)** | Prohibits page from loading if it detects XSS attack | Prevents XSS attacks |
| **X-Frame-Options** | Prevents attackers from "overlaying" their content on webpage | Foils phishing attempts |

### Monitoring and Response Systems

| System | Description |
|--------|-------------|
| **HIDS (Host Intrusion Detection System)** | Software-based application on endpoint that detects attacks have occurred; automated detection; monitors system calls, file system access, host I/O |
| **HIPS (Host Intrusion Prevention System)** | Monitors endpoint activity to immediately block malicious attack by following specific rules; watches for events that control/terminate programs or install devices |
| **EDR (Endpoint Detection and Response)** | More robust than HIDS/HIPS; aggregates data from multiple endpoints to centralized database; performs sophisticated analytics for pattern identification and anomaly detection |

### Hardening Endpoints

#### Patch Management
- **Patching**: installing software security updates — one of the most important steps in securing endpoint
- Threat actors watch for patch release and immediately craft attacks around vulnerability
- Effective patch management involves distribution tools and reception tools

##### Patch Distribution
- Modern OS distribute patches; patches can sometimes create problems (prevent custom applications from running)
- Organizations test patches before installation
- **Automated patch management tools**: manage patches within enterprise instead of relying on vendor's online update service
- Advantages: download from local server (saves bandwidth/time), administrators can approve/decline updates, can force updates by specific date, can obtain reports

##### Patch Reception
- Windows 11 updates less lenient than prior versions; updates can be delayed 1–5 weeks
- Apple macOS has similar features: notification of available updates, choice of when to install

#### Operating System Protections

| Protection | Description |
|-----------|-------------|
| **Disabling unnecessary ports/protocols** | Closing unused ports and disabling unnecessary protocols; turning off unneeded services |
| **Application allow listing** | Approving in advance only specific applications to run on OS; anything not approved will not function |
| **Deny list** | Inverse of allow list — listing of unapproved software so anything not on list can run |
| **Sandbox** | Container in which application can run without impacting underlying OS; contents not saved when closed |

---

## Key Terms

- **Antivirus (AV)** — software examining computer for virus infections and monitoring activity
- **Application allow listing** — approving only specific applications to run on OS
- **Backdoor** — access that circumvents normal security protections
- **Bot (zombie)** — infected computer under remote control of attacker
- **Bloatware** — software installed on device without user requesting it
- **Buffer overflow attack** — storing data in RAM beyond fixed-length buffer boundaries
- **Cookie** — file where server stores user-specific information on user's local computer
- **CSRF (Cross-Site Request Forgery)** — exploiting authentication token to force target to take action
- **Directory traversal** — attack moving from root directory to restricted directories
- **EDR (Endpoint Detection and Response)** — robust monitoring aggregating data from multiple endpoints
- **File-based virus** — malicious code attached to a file
- **Fileless virus** — virus that uses native OS services instead of attaching to files
- **HIDS (Host Intrusion Detection System)** — software detecting attacks on endpoint
- **HIPS (Host Intrusion Prevention System)** — software immediately blocking malicious attacks
- **HSTS (HTTP Strict Transport Security)** — forces browser to use HTTPS
- **Indicator of Attack (IoA)** — sign that an attack is currently underway
- **Keylogger** — captures and stores each keystroke user types
- **LOLBins (living-off-the-land binaries)** — native OS services used by fileless viruses
- **Logic bomb** — code that lies dormant until triggered by specific event
- **Malware** — malicious software designed to interfere with normal functions
- **Patch management** — installing software security updates
- **Privilege escalation** — gaining illicit access of elevated rights
- **Race condition** — two concurrent threads accessing shared resource simultaneously
- **RAT (Remote Access Trojan)** — Trojan giving unauthorized remote access
- **Ransomware** — malicious software extorting money for device restoration
- **Replay attack** — copying and retransmitting data to impersonate user
- **Rootkit** — malware hiding its presence and other malware
- **Sandbox** — container for running applications without impacting OS
- **Secure cookie** — cookie only sent with encrypted HTTPS request
- **SQLi (SQL Injection)** — inserting statements to manipulate database server
- **Spyware** — tracking software deployed without user consent
- **TOC to TOU** — time of check to time of use race condition
- **Trojan** — executable masquerading as benign but performing malicious activity
- **Worm** — malicious program using network to replicate
- **XSS (Cross-Site Scripting)** — attacking websites that accept unsanitized user input

---

## Review Questions

1. What word is the currently accepted term for network-connected hardware devices?
   - a. Host
   - b. Endpoint
   - c. Device
   - d. Client

2. Which of the following is NOT a feature of blocking ransomware?
   - a. A message on the user's screen appears pretending to be from a reputable third party.
   - b. It prevents a user from using their computer in a normal fashion.
   - c. It can be defeated by a double power cycle.
   - d. It is the earliest form of ransomware.

3. Cillian is explaining to an intern why ransomware is considered the most serious malware threat. Which reason would Cillian NOT give?
   - a. Once a device is infected with ransomware, it will never function normally.
   - b. Launching a ransomware attack is relatively inexpensive and does not require a high degree of skill.
   - c. Ransomware attacks occur with a very high frequency.
   - d. Attacks from ransomware have a high impact on organizations.

4. Finn's team leader has just texted him that an employee, who violated company policy by bringing in a file on a USB flash drive, has just reported that their computer is infected with locking ransomware. Why would Finn consider this a serious situation?
   - a. It sets a precedent by encouraging other employees to violate company policy.
   - b. It can encrypt all files on any network that is connected to the employee's computer.
   - c. The organization may be forced to pay up to $500 for the ransom.
   - d. The employee would have to wait at least an hour before their computer could be restored.

5. What is the difference between a keylogger and spyware?
   - a. A keylogger operates much faster than spyware.
   - b. Spyware is illegal while a keylogger is not.
   - c. Spyware typically secretly monitors users but unlike a keylogger makes no attempts to gather sensitive user keyboard input.
   - d. Spyware can be installed using a hardware device while a keylogger cannot.

6. Which of the following is NOT a technology used by spyware?
   - a. Tracking software
   - b. System-modifying software
   - c. Active tracking technologies
   - d. Automatic download of software

7. Which of the following is NOT true about RATs?
   - a. A RAT gives the threat agent unauthorized remote access to the victim's computer.
   - b. A RAT and a worm have the same basic function.
   - c. A RAT allows the attacker to monitor what the user is doing, change settings, browse files, and access other computers.
   - d. A RAT creates an opening into the victim's computer, allowing unrestricted access.

8. Which type of computer virus is malicious computer code that becomes part of a file?
   - a. File-based virus
   - b. Jump virus
   - c. Fileless virus
   - d. RAM-Check virus

9. Which of the following is NOT a Microsoft Windows common LOLBin?
   - a. DLR
   - b. .NET Framework
   - c. Macro
   - d. PowerShell

10. Which type of malware is sometimes called a "network virus" because it enters a computer to move through the network?
    - a. Fileless virus
    - b. Worm
    - c. Trojan
    - d. File-based virus

11. Which of these would NOT be considered the result of a logic bomb?
    - a. Send an email to Rowan's inbox each Monday morning with the agenda of that week's department meeting.
    - b. If the company's stock price drops below $50, credit Oscar's retirement account.
    - c. Erase the hard drives of all servers 90 days after Alfredo's name is removed from employee list.
    - d. Delete all human resource records regarding Augustine one month after he leaves the company.

12. Which attack is based on a website accepting user input without sanitizing it?
    - a. RSS
    - b. XSS
    - c. iSQL
    - d. SSXRS

13. Which attack takes advantage of an authentication token that a website sends to a user's web browser?
    - a. SSFR
    - b. DLLS
    - c. CSRF
    - d. DRCR

14. Which attack manipulates the trusting relationship between web servers?
    - a. SSRF
    - b. CSRF
    - c. EXMAL
    - d. SCSI

15. Which type of memory vulnerability attack manipulates the "return address" of the memory location?
    - a. Pointer attack
    - b. Stuffing attack
    - c. Integer overwrite
    - d. Buffer overflow attack

16. What race condition can result in a NULL pointer/object dereference?
    - a. Conflict race condition
    - b. Value-based race condition
    - c. Thread race condition
    - d. Time of check (TOC) to time of use (TOU)

17. Which of the following would NOT be considered an IoA?
    - a. Resource manipulation
    - b. Out-of-cycle logging
    - c. Account lockout
    - d. Blocked content

18. Nollaig is reviewing the steps that an attacker took when they compromised a web server and accessed confidential files. What type of attack was this?
    - a. Directory traversal
    - b. Account overflow
    - c. Race condition
    - d. TOE

19. Which statement regarding a secure cookie is NOT correct?
    - a. It is a means of protection of a web browser.
    - b. A secure cookie is only sent to the server with an encrypted request.
    - c. It uses the HTTPS protocol.
    - d. It prevents an unauthorized person from intercepting a cookie that is being transmitted.

20. Which statement regarding a keylogger is NOT true?
    - a. Software keyloggers can be designed to send captured information automatically back to the attacker.
    - b. Hardware keyloggers are installed between the keyboard connector and computer keyboard USB port.
    - c. Software keyloggers are generally easy to detect.
    - d. Keyloggers can be used to capture passwords, credit card numbers, or personal information.
