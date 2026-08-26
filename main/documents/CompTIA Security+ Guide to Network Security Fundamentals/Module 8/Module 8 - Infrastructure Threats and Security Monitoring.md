---
created: 2026-08-20 14:30:00
class:
  - document
description: CompTIA Security+ SY0-701 Module 8 — network attacks, security monitoring, and email defenses
mod.: 2026-08-20 14:30:00
aliases:
  - security+ module 8
  - infrastructure threats and security monitoring
tags:
  - study/security-plus
  - study/security-plus/module-8
---

# Module 8 - Infrastructure Threats and Security Monitoring

## Objectives

1. [[#Objective 1 - Attacks on Networks|Describe the different types of attacks on networks]]
2. [[#Objective 2 - Security Monitoring and Alerting|Explain how to perform security monitoring and alerting]]
3. [[#Objective 3 - Email Monitoring and Security|List and describe different email defenses]]

---

## Objective 1 - Attacks on Networks

### Overview
- Threat actors place high priority on targeting networks
- Exploiting a single network vulnerability can expose hundreds or thousands of devices
- Network attacks include: on-path attacks, DNS attacks, DDoS attacks, malicious coding attacks, Layer 2 attacks, and credential relay attacks

### On-Path Attacks

**On-path attack**: threat actor positions themselves in the middle between two communicating users or devices

**Two key advantages:**
- Can occur without targets knowing attacker is present
- Gives attacker flexibility: eavesdrop or modify messages

#### Man-in-the-Middle (MITM)
- Threat actor Eve positions herself between Alice and Bob
- Neither party can detect her presence
- Eve can passively eavesdrop or actively impersonate

**Two challenges for attacker:**
- **Intercepting traffic**: splitting original TCP connection into two new connections (client↔attacker, attacker↔server); altering packet headers in IP address
- **Decrypting transmissions**: sending fake digital certificate to trick computer into verifying authenticity

**Detection focus**: monitoring access to sensitive resources and failed login attempts followed by successful logins

#### Session Replay
- **Replay attack**: variation of MITM; makes copy of legitimate transmission before sending to recipient
- **Session replay attack**: intercepts and uses a **session ID** to impersonate a user
- **Session ID**: unique number web server assigns user for duration of visit; usually at least 128 bits; hashed with SHA-256
- Session IDs can be in URL extensions, hidden form fields, or cookies
- Theft techniques: MITM attacks, XSS, Trojans, malicious JavaScript

#### Man-in-the-Browser (MITB)
- Intercepts and manipulates communication between web browser and underlying computer
- Begins with Trojan infecting computer and installing browser extension
- Extension checks if visited site is targeted; captures form data when user submits
- May modify receipt data so user sees legitimate transaction
- **Advantages for attackers:**
  - Trojan browser extensions provide valid function while installing malware
  - Dormant for months until triggered by visiting targeted site
  - Resides within browser, difficult for standard anti-malware to detect

---

### DNS Attacks

**DNS (Domain Name System)**: hierarchical name system matching computer names to IP addresses

**Two goals of DNS attacks:**
- **URL redirection**: user redirected to fictitious site (e.g., fake bank)
- **Domain reputation attack**: competitor uses DNS attack to cause rival's domain to earn low reputation score

#### DNS Poisoning
- Modifies **local host file** on device to point to different domain
- Host files: `/etc/` in UNIX/Linux/macOS; `Windows\System32\drivers\etc` in Windows
- Instead of multiple entries, attacker adds single entry redirecting to malicious DNS server
- Attacker's DNS server contains all malicious mappings
- Advantages: all domains one victim uses can be controlled

#### DNS Hijacking
- Infects **external DNS server** with IP addresses pointing to malicious sites
- Exploits zone transfers (DNS servers exchanging information)
- If DNS server doesn't validate DNS responses, accepts fraudulent entries
- **Advantages:** all users accessing that DNS server will be redirected

---

### Distributed Denial of Service (DDoS) Attack

**DoS attack**: bombards system with extremely high number of fake requests

**DDoS attack**: hundreds, thousands, or millions of sources producing torrent of fake requests

**Targets:** web servers, networks, cloud-based resources, infrastructure (power grids)

#### Two Methods of Generating Attack Data

| Method | Description |
|--------|-------------|
| **Botnet of compromised devices** | Includes computers, servers, IoT devices (baby cameras, garage openers); 1 million IoT devices could send 4 Tbps |
| **Amplified attacks (reflection)** | Attackers point data cannons at misconfigured devices; device reflects larger payload at target |

**Common reflection amplification targets:**
- **NTP (Network Time Protocol)**: 206-fold increase in throughput
- **Memcached**: database caching system; attacks 51,000× their original size

**Notable DDoS facts:**
- 2016: 145,607 compromised IoT devices flooded French hosting service with 1.1 Tbps
- Current record: 3.47 Tbps from over 10,000 sources in 10+ countries
- DDoS services available to anyone at low price (botnet of 300-Gbps attack for $20)
- ~90% of ~7 million annual DDoS attacks are gamers retaliating against other players

---

### Malicious Coding and Scripting Attacks

#### PowerShell
- Microsoft task automation and configuration management framework
- Can inject code into other processes without storing to hard drive
- Commands execute bypassing security protections; virtually no evidence
- Can be configured to avoid anti-malware detection
- Trusted application → actions rarely scrutinized

#### Visual Basic for Applications (VBA)
- Event-driven Microsoft programming language built into Office applications
- Used to create **macros** (series of instructions grouped as single command)
- 98% of Office-targeted threats are macro-based malware
- **Best practice:** disable macros unless business requirement; only allow digitally signed macros from trusted publishers

#### Python
- Popular programming language running on multiple OS platforms
- Fewer lines of code than Java/C++; object-oriented; large standard library
- **Best practices:** use latest version, stay current on vulnerabilities, careful with string formatting, download only vetted libraries

#### Bash
- Command language interpreter (shell) for Linux/UNIX OS
- **Bash scripting**: creating scripts (interpreted and executed without compilation)
- Vulnerabilities exploited: e.g., malicious executable attached to variable executed when Bash invoked

---

### Layer 2 Attacks

**OSI Model**: 7-layer reference model for networking; each layer works without knowledge of other layers

**Layer 2 (Data Link Layer)**: particularly weak; responsible for dividing data into packets, error detection, physical addressing, data framing

#### ARP Poisoning
- **ARP (Address Resolution Protocol)**: maps logical IP addresses to physical MAC addresses
- Sending endpoint broadcasts ARP request; endpoint with that IP responds with MAC address; stored in ARP cache
- **ARP poisoning**: threat actor changes ARP cache data so IP points to different device
- Uses **spoofing** (deceiving by impersonating another's identity)
- Successful because no authentication procedures verify ARP requests/replies

#### MAC Attacks

| Attack | Description |
|--------|-------------|
| **MAC cloning** | Attacker discovers valid MAC address, spoofs it on their device, sends packet; switch updates MAC table to attacker's port |
| **MAC flooding** | Overflow switch with spoofed packets (each with different source MAC); consumes all CAM (content addressable memory); switch enters failure mode |

**Switch Failure Modes:**

| Mode | Description | Security Implication |
|------|-------------|---------------------|
| **Fail closed** | Shuts down when failure detected | Security over access |
| **Fail open** | Continues operations normally; broadcasts frames to all ports | Access over security; enables sniffing |
| **Fail safe** | Protects all other components via bypass switch | Adds separate device |
| **Failover** | Recovers functionality through redundancy | Uses redundant devices |

---

### Credential Relay Attack
- Attempts to steal authentication credentials and use them to access system
- Intercepts digests of user passwords during transmission
- **Process:**
  1. Bob tricked into attempting to sign in to Eve's computer
  2. Eve captures Bob's authentication digest
  3. Eve uses Bob's digest to sign in to valid server

---

## Objective 2 - Security Monitoring and Alerting

### Monitoring Methodologies

| Methodology | Description | Advantages | Limitations |
|------------|-------------|------------|-------------|
| **Anomaly-based** | Establishes secure baseline; alarms on significant deviation | Detects anomalies quickly | Normal behavior changes; baselines need updating |
| **Signature-based** | Looks for well-known patterns against predefined signature database | Matches known threats | Requires constant database updates |
| **Behavior-based** | Uses normal processes as standard; alerts on abnormal actions | No signature updates needed; stops new attacks quickly | May generate false positives |
| **Heuristic-based** | Uses algorithm to determine if threat exists; answers "will this do something harmful?" | Catches applications others miss | May have higher false positive rate |

---

### Monitoring Activities

| Activity | Description |
|----------|-------------|
| **Scanning** | Frequent, often automated process that continuously searches for evidence of attack |
| **Reporting** | Generating documentation on results of monitoring activities |
| **Quarantine** | Isolating systems that have been compromised |
| **Alerting** | Detecting and notifying operators about meaningful events |
| **Alert tuning** | Tweaking alerting function to weed out false positives |
| **Archiving** | Retaining historical documents and records of monitoring |

---

### Tools for Monitoring and Alerting

#### Packet Capture and Replay Tools
- Examines entire packet contents (header + payload)
- Analyzes multiple packets to piece together information
- **Uses:** troubleshooting connectivity, examining application sessions, solving DHCP issues
- **Security uses:** detect unusual behavior (high DNS responses), search for unusual domains/IPs, discover regular connections to C&C servers

| Tool | Description |
|------|-------------|
| **Wireshark** | GUI-based packet capture and analysis tool |
| **Tcpdump** | Command-line packet analyzer for UNIX/Linux |
| **Tcpreplay** | Tool for editing and replaying packets onto network |

#### Flow Analysis (Network Traffic Analysis)
- Monitors network's different devices; alerts if exceeds predefined baseline
- Identifies performance bottlenecks and which applications use bandwidth

**Security advantages over traditional analysis:**
- **Eliminates monitoring agents** (agentless): threat actors can't disable; works on devices that can't accept agents (database servers, IoT, embedded systems)
- **Uses deep packet inspection**: extracts metadata, converts to readable format; can decrypt application traffic
- **Provides richer information**: identifies active devices, applications, protocols, data being accessed

**Flow analysis data sources:**

| Source | Description |
|--------|-------------|
| **NetFlow** | Session sampling protocol on Cisco routers; collects IP traffic; uses ICMP Echo request |
| **sFlow** | Packet sampling protocol; statistical sampling instead of actual packet flow |
| **IPfix** | Similar to NetFlow but adds SNMP information directly |

**Key use:** detecting ransomware (multiple files being changed simultaneously)

#### Data Loss Prevention (DLP)
- System of security tools to recognize, identify, and protect critical data
- Monitors who uses data, how accessed; alerts and blocks restricted data export
- Considered **rights management** (owner authority to impose restrictions)

**Inspection methods:**
- **Content inspection**: security analysis within approved context; looks at security level, who requesting, where stored, when requested, where going
- **Index matching**: complex computations on protected documents; recognizes leaked snippets

**DLP actions:** blocking data, redirecting to examiner, quarantining, alerting supervisor

**Limitations:** rules must be continually created and maintained; increasingly uses machine learning

#### SNMP Traps
- **SNMP (Simple Network Management Protocol)**: manages network equipment; allows remote monitoring, management, configuration
- Found on switches, routers, WAPs, printers, copiers, UPSs
- **SNMP trap**: unsolicited message or notification about critical events in managed device

#### Log Aggregation
- **Log**: record of events in organization's systems/networks
- **Syslog**: standard message format for network devices to communicate with logging server
- **Log consolidation**: gathering events from disparate sources into single entity for analysis

#### SCAP (Security Content Automation Protocols)
- Collection of open security standards; considered security benchmarks
- Automates vulnerability management; determines policy compliance
- SCAP-compliant applications check systems for vulnerabilities and misconfigurations
- Interoperates with other SCAP-validated scanners; results in standardized format

#### SIEM (Security Information and Event Management)
- Consolidates real-time security monitoring with analysis and reporting of security events
- Can be separate device, software, or third-party service

**SIEM features:**

| Feature | Description |
|---------|-------------|
| **Aggregation** | Combines data from multiple sources (network devices, servers, applications) |
| **Correlation** | Searches aggregated data for common characteristics (e.g., multiple attacks from same source) |
| **Automated alerting and triggers** | Informs security personnel of critical issues (e.g., "Alert on 40+ drop events from same IP in 60 seconds") |
| **Time synchronization** | Shows order of events across wide spectrum of time |
| **Event duplication** | Filters multiple alerts into single alarm when same event detected by multiple devices |
| **Logs** | Retains records for future analysis and compliance |

**Advanced SIEM capabilities:**
- **User behavior analysis**: detects unusual account behavior (e.g., lateral movement between assets)
- **Sentiment analysis**: identifies and categorizes opinions in textual data; tracks threat actor postings in forums; predicts future attacks

#### SOAR (Security Orchestration, Automation, and Response)
- Similar to SIEM but goes further with comprehensive data gathering and analytics
- Automates incident responses
- While SIEM generates more alerts than team can respond to, SOAR automates responses

---

## Objective 3 - Email Monitoring and Security

### How Email Works

#### Email Components

| Component | Description |
|-----------|-------------|
| **MUA (Mail User Agent)** | Used to read and send mail from endpoint (Thunderbird, Gmail, Outlook) |
| **MTA (Mail Transfer Agent)** | Programs that accept email messages and route toward recipients |

#### Email Protocols

| Protocol | Purpose |
|----------|---------|
| **SMTP** | Originally used to send email to mail server |
| **POP3** | Downloaded email from server (replaced by IMAP) |
| **IMAP** | Allows email to remain on server; read from multiple endpoints; organize into folders |
| **Webmail** | Website as MUA (Gmail); no SMTP/IMAP configuration needed |

#### Email Headers
- Information added as email transfers from MTA to MTA
- Contains: sender, recipient, email's route through MTAs, authentication details
- Each MTA adds its own information to the **top** of header
- Reading from top down: destination MTA → ... → sender MTA

#### Microsoft Office 365 Email Analysis Categories

| Abbreviation | Category |
|-------------|----------|
| BULK | Bulk |
| DIMP | Domain impersonation |
| GIMP | Mailbox intelligence-based impersonation |
| HPHISH | High-confidence phishing |
| HSPM | High-confidence spam |
| MALW | Malware |
| PHSH | Phishing |
| SPM | Spam |
| SPOOF | Spoofing |
| UIMP | User impersonation |
| AMP | Anti-malware |
| SAP | Safe attachments |
| OSPM | Outbound spam |

---

### Email Threats

| Threat | Description |
|--------|-------------|
| **Malicious payload** | Email contains attack (malicious attachment); launching it launches attack; also includes invoice scams |
| **Embedded links** | Links in HTML email; displayed link differs from underlying hyperlink (your-bank.com → steal-your-money.net) |
| **Impersonation** | Threat actor gains access to executive's email; sends malicious emails pretending to be that person |
| **Forwarding** | Users auto-forward corporate emails to personal accounts; risks: sensitive data distributed outside corporate environment; "replay" attacks; legal evidence issues |

---

### Email Defenses

#### Sender Policy Framework (SPF)
- Email authentication method identifying authorized MTA email servers for a domain
- Admin owner sets **TXT record** in DNS stating which servers are allowed to send mail
- Helps protect domain from spoofing; prevents valid emails from being marked as spam
- **SoftFail warning**: trust message less but don't completely invalidate
- **Limitation:** no means of protecting SPF information once generated

#### Domain Keys Identified Mail (DKIM)
- Validates content of email message itself through **digital signature**
- Admin owner generates asymmetric public/private key pair
- Public key stored in TXT record on domain's DNS
- Mail servers use private key to generate digital signature (encrypted digest) of entire message body
- Recipients decrypt DKIM signature using public key from DNS; verifies digests match

#### Domain-Based Message Authentication, Reporting, and Conformance (DMARC)
- Extends SPF and DKIM
- Allows admin owner to publish DNS policy specifying mechanism (DKIM, SPF, or both) used when sending email
- Indicates how to check From: field presented to end-users
- Provides reporting mechanism for actions under those policies

#### Secure Email Gateway (SEG)
- Filters all incoming email through proxy for organization's email server
- Malicious email deleted; approved email forwarded to corporate server
- Configured by setting DNS MX record to point to SEG

**SEG limitations:**

| Limitation | Description |
|-----------|-------------|
| **Single-layer security** | May disable built-in security protections from Google/Microsoft; negates defense-in-depth |
| **Exposing protections** | Changing DNS MX record may enable attackers to tailor attacks |
| **Multiple root domains** | Attackers send emails to root domains managed by Google/Microsoft, bypassing SEG |

---

## Key Terms

- **Agentless** — network data collection without monitoring agents
- **Amplified attacks** — reflection attacks using misconfigured devices to increase payload
- **ARP poisoning** — modifying ARP cache so IP points to different device
- **Credential relay attack** — stealing authentication credentials and using them to access system
- **DLP (Data Loss Prevention)** — security tools to recognize and protect critical data
- **DDoS (Distributed Denial of Service)** — attack using hundreds/thousands/millions of sources
- **DNS attacks** — substituting DNS address to redirect computers
- **DKIM** — validates email content through digital signature
- **DMARC** — extends SPF/DKIM with policy and reporting
- **Fail closed/open/safe/failure mode** — switch behaviors on failure
- **Log aggregation** — consolidating events from multiple sources for analysis
- **MAC cloning/flooding** — Layer 2 attacks manipulating switch MAC address tables
- **MITM (Man-in-the-Middle)** — intercepts communication between two parties
- **MITB (Man-in-the-Browser)** — intercepts/manipulates browser-computer communication
- **NetFlow** — Cisco session sampling protocol for network traffic analysis
- **On-path attack** — attacker positioned between communicating parties
- **Packet capture** — collecting and analyzing network data packets
- **Phishing** — fraudulent email to steal credentials
- **Replay attack** — copying legitimate transmission for later reuse
- **SCAP** — open security standards for vulnerability management
- **SEG (Secure Email Gateway)** — email filtering proxy
- **Session ID** — unique number for user's visit duration
- **SIEM** — consolidates security monitoring with analysis and reporting
- **SNMP trap** — unsolicited notification about critical device events
- **SOAR** — automates incident responses
- **SPF** — identifies authorized MTA email servers for a domain
- **Syslog** — standard message format for network device logging

---

## Review Questions

1. Which attack intercepts communications between a web browser and the underlying OS?
   - a. MITM
   - b. MRTR
   - c. MTTR
   - d. MITB

2. Himari needs to protect against potential attacks on DNS. What are the locations she would need to protect?
   - a. Web server buffer and host DNS server
   - b. Reply referrer and domain buffer
   - c. Web browser and browser add-on
   - d. Local host file and external DNS server

3. What is the result of an ARP poisoning attack?
   - a. The ARP cache is compromised
   - b. Users cannot reach a DNS server
   - c. MAC addresses are altered
   - d. An internal DNS must be used instead of an external DNS

4. Yua has discovered that the network switch is broadcasting all packets to all devices. She suspects it is the result of an attack that has overflowed the switch MAC address table. Which type of attack would she report?
   - a. MAC spoofing attack
   - b. MAC cloning attack
   - c. MAC flooding attack
   - d. MAC overflow attack

5. Sakura is explaining to a colleague the different types of DNS attacks. Which DNS attack would only impact a single user?
   - a. DNS hijack attack
   - b. DNS poisoning attack
   - c. DNS overflow attack
   - d. DNS resource attack

6. Which type of monitoring methodology looks for statistical deviations from a baseline?
   - a. Behavioral monitoring
   - b. Signature-based monitoring
   - c. Anomaly monitoring
   - d. Heuristic monitoring

7. Ichika suspects that there may be infected devices on the network that are sending regular beacons to a threat actor's C&C server. Which type of analysis would she use?
   - a. Traffic analysis
   - b. Port analysis
   - c. Packet analysis
   - d. Probe analysis

8. Akari has been asked to install a packet analysis tool on a Linux web server. The server has no GUI—only command-line applications. Which tool would Akari install?
   - a. Ethereal
   - b. Tcpdump
   - c. Network General
   - d. Sniffer

9. Which is NOT a reason threat actors use PowerShell for attacks?
   - a. It cannot be detected by anti-malware running on the computer
   - b. It leaves behind no evidence on a hard drive
   - c. It can be invoked prior to system boot
   - d. Most applications flag it as a trusted application

10. Which attack uses the fewest number of computers to launch the attack?
    - a. DoS
    - b. DDoS
    - c. DoSS
    - d. DooS

11. Which of the following is used to write macros?
    - a. PowerShell
    - b. Python
    - c. Bash
    - d. VBA

12. Which is NOT correct about an email header?
    - a. As email is transferred from MTA to MTA, information is added to the email header
    - b. Email headers are encrypted to prevent someone from altering the contents
    - c. The email header contains information about the sender, recipient, email's route through MTAs, and various authentication details
    - d. Each MTA along the path adds its own information to the top of the email header

13. Which is NOT correct about forwarding emails?
    - a. Corporations routinely allow employees to forward emails
    - b. Employees may "auto-forward" corporate emails to utilize enhanced spam filtering
    - c. Forwarded emails may not be available for email evidence
    - d. Unauthorized users could access forwarded emails

14. Which email defense uses a digital signature?
    - a. SPC
    - b. DKIM
    - c. DMARC
    - d. It depends on whether or not the email payload has been encrypted

15. Aoi uses Python and does not want her code to contain vulnerabilities. Which best practice would she NOT use?
    - a. Only use compiled and not interpreted Python code
    - b. Use the latest version of Python
    - c. Use caution when formatting strings
    - d. Download only vetted libraries

16. What is Bash?
    - a. The command-language interpreter for Linux/UNIX OSs
    - b. The open-source scripting language that contains many vulnerabilities
    - c. A substitute for SSH
    - d. The underlying platform on which macOS is built

17. Which tool edits packets and replays them onto the network to observe behavior?
    - a. Tcpreplay
    - b. Tcpdump
    - c. Wireshark
    - d. Packetdump

18. Which is NOT a limitation of an SEG?
    - a. Slow processing speed
    - b. Single-layer security
    - c. Multiple root domains
    - d. Revealing protections

19. Amari has been asked to compare an organization's security against open security standards. Which would he choose?
    - a. SCAP
    - b. NFLOW
    - c. SOAR
    - d. SPF

20. What does an SNMP trap do that is different from normal SNMP function?
    - a. SNMP traps do not use PDU
    - b. SNMP traps can only respond to administrator queries once per hour
    - c. SNMP traps can send unsolicited messages
    - d. SNMP traps require authentication while normal SNMP does not
