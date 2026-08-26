---
created: 2026-08-20 15:00:00
class:
  - document
description: CompTIA Security+ SY0-701 Module 9 — security appliances, software protections, secure design, and access technologies
mod.: 2026-08-20 15:00:00
aliases:
  - security+ module 9
  - infrastructure security
tags:
  - study/security-plus
  - study/security-plus/module-9
---

# Module 9 - Infrastructure Security

## Objectives

1. [[#Objective 1 - Security Appliances|List the different types of security appliances and how they can be used]]
2. [[#Objective 2 - Software Security Protections|Describe security software protections]]
3. [[#Objective 3 - Secure Infrastructure Design|Explain how a secure design can aid in mitigating attacks]]
4. [[#Objective 4 - Access Technologies|Describe different access technologies and how they can be used]]

---

## Objective 1 - Security Appliances

### Mitigation Principles

| Principle | Description |
|-----------|-------------|
| **Gap analysis** | Comparison of current state of information security with recommended controls |
| **Segmentation** | Dividing network into multiple subnets with each acting as own small network |
| **Isolation** | Keeping multiple instances of attack surface separate |
| **Least privilege** | Granting access limited to what is necessary |
| **Configuration enforcement** | Applying security measures to reduce unnecessary vulnerabilities |
| **Decommissioning** | Removing technology or service from live production environment |
| **Removal of unnecessary software** | Deleting software not essential to operation |
| **Selection of effective controls** | Choosing safeguards to limit asset exposure |
| **Device placement** | Physically locating devices in secure locations |

---

### Common Network Devices

#### Hubs (Legacy)
- Standard network device for connecting multiple devices to function as single network segment
- Operated at Physical Layer (Layer 1); did not read data bits
- Multiport repeater: received and passed all PDUs to all connected devices
- **Security risk:** threat actor could capture and decode all PDUs on any connected client
- Rarely used today except in time-critical applications (no buffering → faster than switches: 100–350 ns vs ~10,000 ns)

#### Switches
- Operating at Data Link Layer (Layer 2); has "intelligence"
- Learns which device connected to each port by examining MAC address
- Stores MAC address table; forwards frames only to intended device
- Better security than hub: attacker sees only packets directed to their device

**Port Security:**
- Limits number of MAC addresses learned on ports
- **Restrict mode:** ignores new MAC addresses; allows only preapproved MAC
- **Sticky mode:** records new MAC addresses up to specific limit
- **Shutdown mode:** blocks port entirely
- Prevents unauthorized switches and devices from connecting to corporate network

**Switch Configuration Defenses:**

| Attack | Defense |
|--------|---------|
| MAC flooding | Use switch that closes ports with too many MAC addresses |
| MAC address spoofing | Configure only one port per MAC address |
| ARP poisoning | Use ARP detection appliance |
| Port mirroring | Secure switch in locked room |

#### Routers
- Operating at Network Layer (Layer 3); forwards frames across different networks
- Security function: **Access Control Lists (ACLs)** — rules functioning as network filter
- **External router ACLs:** restrict vulnerable protocols, limit traffic from unapproved networks, anti-spoofing
- **Internal router ACLs:** less restrictive but more specific; explicit permit/deny for specific addresses and protocols

#### Servers
- Distributes resources and services to network devices
- Compromised server = access to privileged contents + opening for attacks to other devices

**Server hardening steps:**
1. Apply patches to vulnerabilities immediately
2. Monitor the server continually
3. Control access permissions (least privilege)
4. Remove unnecessary software
5. Secure the server location

#### Load Balancers
- Distributes work evenly across network; allocates requests across multiple servers
- Reduces probability of overloading single server; optimizes bandwidth

| Type | Description |
|------|-------------|
| **Layer 4** | Acts on Network and Transport Layer protocols (IP, TCP, FTP, UDP) |
| **Layer 7** | Distributes based on Application Layer protocols (HTTP) |

**Security advantages:** detect and stop attacks; hide HTTP error pages; remove server identification headers

---

### Infrastructure Security Hardware

#### Firewalls

**Firewall functions:**
- Bidirectional inspection of outgoing and incoming packets
- Allows approved packets; takes actions on suspicious packets
- **Rule-based firewall:** actions based on specific criteria/rules

**Firewall rule parameters:**
- Source/destination address (IP, MAC, hostname)
- Source/destination port
- Protocol (TCP, UDP, ICMP, IP)
- Direction (Incoming, Outgoing, Both)
- Priority, time, context
- **Action:** Allow, Bypass, Deny, Force Allow, Log Only

**Firewall categories:**

| Category | Options |
|----------|---------|
| Implementation | Hardware vs. Software |
| Scope | Host vs. Appliance vs. Virtual |
| Licensing | Open source vs. Proprietary |
| Filtering | Stateless vs. Stateful |
| Dedicated vs. | Network ACL |

**Key firewall types:**
- **Host-based firewall:** software firewall on single endpoint; application-centric
- **Appliance firewall:** separate hardware device protecting entire network
- **Virtual firewall:** runs in cloud for public cloud environments
- **Stateless packet filtering:** examines packet against rules only (Layer 3)
- **Stateful packet filtering:** uses rules + connection state; checks "Did internal device request this?" (Layer 4)
- **Policy-based firewall:** allows generic statements instead of specific rules (more flexible)

**Specialized firewalls:**

| Type | Description |
|------|-------------|
| **WAF (Web Application Firewall)** | Examines HTTP applications; blocks XSS and SQL injection |
| **NGFW (Next-Generation Firewall)** | Deep packet inspection; application filtering; URL filtering; intrusion prevention |
| **UTM (Unified Threat Management)** | Combines: packet filtering, antispam, antiphishing, antispyware, encryption, intrusion protection, web filtering |
| **Layer 7 firewall** | Investigates packet contents for malware |
| **NAT gateway** | Cloud-based; performs NAT; masks internal IP addresses |

#### Proxy Servers

| Type | Description |
|------|-------------|
| **Forward proxy** | Intercepts internal user requests; processes on behalf of user; uses own IP address; provides caching, speed, cost reduction, security |
| **Reverse proxy** | Routes external requests to correct internal server; only reverse proxy can access internal servers |

**Forward proxy advantages:** increased speed (cache), reduced bandwidth costs, improved management (block websites), stronger security (hide client IP)

#### Deception and Disruption Instruments

**Lures:**

| Type | Description |
|------|-------------|
| **Honeypot** | Computer in low-security area configured with vulnerabilities as bait; goals: deflect and discover attack techniques |
| **Low-interaction honeypot** | Only contains login prompt; records attempts and IP addresses |
| **High-interaction honeypot** | Captures more information; includes honeyfiles and fake telemetry |
| **Honeynet** | Network with intentional vulnerabilities; contains one or more honeypots |
| **Honeytoken** | Fake data added to live production systems for tracing |

**Sinkholes:**

| Type | Description |
|------|-------------|
| **Sinkhole** | "Bottomless pit" steering unwanted traffic away from intended destination |
| **DNS sinkhole** | Changes DNS request to preconfigured IP with deny-all firewall rule; commonly counters DDoS attacks |

#### IDS/IPS

| System | Function | Connection | Blocking |
|--------|----------|------------|----------|
| **IDS (Intrusion Detection System)** | Detects attack; sounds alarm (passive) | Connected to switch port; receives copy of traffic | Cannot block attacks |
| **IPS (Intrusion Prevention System)** | Automatically blocks attack (active) | Inline; directly connected to network | Can block attacks |

| Type | Description |
|------|-------------|
| **NIDS** | Network IDS; sensors on firewalls/routers monitor traffic; report to central device |
| **NIPS** | Network IPS; located inline on firewall; blocks attacks immediately |

---

## Objective 2 - Software Security Protections

### Web Filtering
- Monitors websites users browse; allows or blocks web traffic

**Web filtering software locations:**

| Type | Description |
|------|-------------|
| **Browser scanning** | Extensions/add-ons; lightweight; not robust for enterprise |
| **Agent-based scanning** | Resides on endpoint device |
| **Centralized proxy scanning** | All requests funneled through proxy appliance |
| **Cloud scanning** | Cloud-based solution; filters traffic from remote users |

**Web filtering methods:**

| Method | Description |
|--------|-------------|
| **Content categorization** | Websites classified into categories (1,000+ categories); blocks by category |
| **URL scanning** | Separate service scanning web for malicious URLs; creates block database |
| **Reputation score (WBRS)** | Website assigned score based on safety; factors: URL category, age, history, domain reputation |

### DNS Filtering
- Blocks harmful content by blocking entire domains (not just individual pages)
- DNS resolver refuses to resolve queries for domains on blocklist
- More efficient than web filtering: one block rule closes entire domain

### File Integrity Monitoring (FIM)
- Monitors files for changes indicating cyberattack
- Establishes baseline for "clean" files; examines: changed, when, how, who, what restoration
- Used for malware detection and regulatory compliance (PCI DSS)
- **Limitation:** high volume of "noise" from frequent benign changes

### Extended Detection and Response (XDR)
- Goes beyond EDR (which aggregates endpoint data)
- Collects and correlates data across: servers, email systems, cloud repositories, endpoints
- Higher visibility and context; reduces false positives; reveals advanced threats
- Typically: software agents on devices connected to cloud-based analysis engine

---

## Objective 3 - Secure Infrastructure Design

### What Is Secure Infrastructure Design?
- Network designed like office building: some areas general access, others successively tighter restrictions
- **Security zones:** different levels of access create higher security through design
- **Air-gapped network:** physically isolated from all other networks/Internet

**Two approaches to infrastructure separation:**

| Approach | Description |
|----------|-------------|
| **Physical segmentation** | Breaking network into smaller subnets; physical appliance as gateway; fixed topology |
| **Logical segmentation** | Creating subnets via virtual networks or addressing schemes; no wiring needed; automated provisioning |

### Virtual LANs (VLANs)
- Logical segmentation allowing scattered users to be grouped together
- Users on different switches can be in same VLAN
- Reduces network traffic; provides security through isolation
- **Tagging protocol:** IEEE 802.1Q adds field to packet identifying VLAN membership
- Prevents direct server communication; all traffic goes through default gateway for inspection

### Demilitarized Zone (DMZ)
- Separate network resting outside secure network perimeter
- Untrusted users can access DMZ but cannot enter secure network
- Contains public-facing servers (web, email)

**DMZ configurations:**

| Configuration | Description |
|--------------|-------------|
| **Single firewall** | Three interfaces: Internet, DMZ, internal LAN; single point of failure |
| **Two firewalls (screened subnet)** | Attacker must breach two firewalls; more secure |
| **Jump server** | Minimally configured admin server within DMZ; connects two dissimilar security zones; tightly restricted access |
| **SAW (Secure Admin Workstation)** | Dedicated workstation for connecting to jump server; prevents compromised admin computer from affecting DMZ |

**Other security zones:**

| Zone | Description | Security Benefit |
|------|-------------|-----------------|
| **Intranet** | Private organization network; approved internal users only | Closed to outside public |
| **Extranet** | Private network accessible to authorized external partners | Enhanced security vs. public website |
| **Guest network** | Separate open network; anyone can access | Permits web surfing without using secure network |

### Zero Trust
- Strategic initiative assuming network is already infected
- "Never trust, always verify"
- Eliminates implicit trust from network architecture
- Prevents lateral movement by threat actors

**Zero Trust Architecture (ZTA) components:**

| Component | Description |
|-----------|-------------|
| **Subject** | User or device requesting access |
| **Adaptive identity** | Verifies more than username/password; includes role, location, resources, prior behavior |
| **Policy engine** | Part of PDP; provides input to PEP |
| **Policy enforcement point (PEP)** | Makes decision whether to grant access |
| **Control plane** | Communication channel |
| **Data plane** | Resource transfer if approved |

- U.S. executive order (2022) mandated all government agencies achieve zero-trust goals by end of FY 2024

---

## Objective 4 - Access Technologies

### Remote Access
- Accessing network infrastructure from non-campus location
- Requires secure connection: protocol selection, port selection

### Virtual Private Network (VPN)
- Enables authorized users to use unsecured public network as if secure private network
- Encrypts **all data** transmitted between remote endpoint and network

**VPN types:**

| Type | Description |
|------|-------------|
| **Remote access VPN** | User-to-LAN connection for remote users |
| **Site-to-site VPN** | Multiple sites connect to other sites over Internet |
| **Always-on VPN** | User stays continuously connected |

**Tunnel types:**

| Type | Description |
|------|-------------|
| **Full tunnel** | All traffic sent to VPN concentrator and protected |
| **Split tunnel** | Only some traffic over VPN; other traffic directly accesses Internet (preserves bandwidth) |

**VPN protocols:**

| Protocol | Description |
|----------|-------------|
| **IPsec** | Common VPN protocol |
| **SSL/TLS** | Common but weaker than IPsec |
| **L2TP** | No encryption alone; usually paired with IPsec (L2TP/IPsec) |
| **HTML5** | "Clientless" VPN; no additional software required |
| **Others** | OpenVPN, SoftEther, WireGuard, SSTP, IKEv2/IPsec |

### Network Access Control (NAC)
- Examines current state of endpoint before network connection
- Devices not meeting criteria: denied access, restricted access, or quarantine network
- Goal: prevent computers with suboptimal security from infecting others

**NAC types:**

| Type | Description |
|------|-------------|
| **Host agent health check** | Software agents installed on endpoints |
| **Permanent NAC agent** | Resides on end devices until uninstalled |
| **Dissolvable NAC agent** | Disappears after reporting to NAC |
| **Agentless NAC** | Embedded in Active Directory; scans device when joining domain |

**NAC process:**
1. Client performs self-assessment using System Health Agent (SHA)
2. Statement of Health (SoH) sent to Health Registration Authority (HRA)
3. HRA integrates with antivirus/patch management servers
4. If approved: Health Certificate issued
5. Certificate presented to network servers
6. If not approved: connected to quarantine network for remediation

**NAC uses ARP poisoning and DNS poisoning** to redirect infected endpoints away from production network

---

## Key Terms

- **Adaptive identity** — verification considering role, location, resources, behavior
- **Air-gapped network** — physically isolated from all other networks
- **Centralized proxy scanning** — web filtering through proxy appliance
- **Content categorization** — classifying websites into 1,000+ categories
- **Control plane** — communication channel in ZTA
- **Data plane** — resource transfer channel in ZTA
- **DNS filtering** — blocking entire domains via DNS resolver
- **FIM (File Integrity Monitoring)** — detects file changes indicating attack
- **Firewall** — bidirectional inspection of network packets
- **Honeypot** — computer baited with vulnerabilities to attract attackers
- **Honeytoken** — fake data on live production systems
- **Honeynet** — network with intentional vulnerabilities
- **IDS (Intrusion Detection System)** — detects attacks; sounds alarm (passive)
- **IPS (Intrusion Prevention System)** — automatically blocks attacks (active)
- **Jump server** — minimally configured admin server within DMZ
- **Load balancer** — distributes work across network
- **NAC (Network Access Control)** — examines endpoint state before network connection
- **NGFW (Next-Generation Firewall)** — deep packet inspection; application filtering
- **NIDS/NIPS** — network-based IDS/IPS
- **Policy-based firewall** — allows generic statements instead of specific rules
- **Port security** — limits MAC addresses learned on switch ports
- **Reverse proxy** — routes external requests to correct internal server
- **Forward proxy** — intercepts internal requests; processes on behalf of user
- **SAW (Secure Admin Workstation)** — dedicated workstation for jump server access
- **Screened subnet** — DMZ with two firewalls
- **Sinkhole** — steers unwanted traffic away from intended destination
- **Stateful packet filtering** — examines rules + connection state (Layer 4)
- **Stateless packet filtering** — examines packet against rules only (Layer 3)
- **UTM (Unified Threat Management)** — combines multiple security functions
- **VLAN (Virtual LAN)** — logical grouping of scattered users
- **VPN (Virtual Private Network)** — encrypts all data between endpoint and network
- **WAF (Web Application Firewall)** — examines HTTP applications
- **WBRS (Web Reputation Score)** — website safety rating
- **XDR (Extended Detection and Response)** — correlates data across network appliances
- **Zero trust** — "Never trust, always verify"; assumes network already compromised
- **ZTA (Zero Trust Architecture)** — framework implementing zero trust

---

## Review Questions

1. Which of the following is NOT true about VPNs?
   - a. It encrypts all data transmitted between remote endpoint and network
   - b. A remote access VPN is a user-to-LAN connection
   - c. A full tunnel routes only some traffic over the secure VPN
   - d. There are a variety of protocols that can be used for VPNs

2. Which firewall rule action implicitly denies all other traffic unless explicitly allowed?
   - a. Force Allow
   - b. Force Deny
   - c. Bypass
   - d. Allow

3. Which of the following is NOT true about zero trust?
   - a. Zero trust assumes networks have already been infiltrated
   - b. Zero trust is designed to make a system trusted
   - c. The motto is "Never trust, always verify"
   - d. Zero trust acknowledges implicit trust is a vulnerability

4. Maya needs a firewall that allows generic statements instead of specific rules. What type should she consider?
   - a. Content/URL filtering firewall
   - b. Policy-based firewall
   - c. Hardware firewall
   - d. Proprietary firewall

5. Astri notes that packets are being dropped for incoming packets the internal endpoint did not initially request. What kind of firewall is this?
   - a. Stateful packet filtering
   - b. Connection-aware firewall
   - c. Proxy firewall
   - d. Packet-filtering firewall

6. What is a virtual firewall?
   - a. A firewall that runs in the cloud
   - b. A firewall that runs in an OS contained as part of an appliance
   - c. A firewall that runs in a sandbox
   - d. A firewall appliance that runs on a LAN

7. Which appliance provides the broadest protection by combining several security functions?
   - a. NAT
   - b. UTM
   - c. WAF
   - d. NGFW

8. Which firewall allows for the most advanced traffic filtering?
   - a. Layer 4 firewall
   - b. Layer 5 firewall
   - c. Layer 6 firewall
   - d. Layer 7 firewall

9. Ada is researching DDoS mitigations. Which should she consider?
   - a. DDoS Prevention System (DPS)
   - b. DNS sinkhole
   - c. MAC pit
   - d. IP denier

10. Which device routes requests from external network to correct internal server?
    - a. Forward proxy server
    - b. Reverse proxy server
    - c. Lateral proxy server
    - d. Neutral proxy server

11. Which would NOT be true regarding a DMZ?
    - a. It can be configured with one or two firewalls
    - b. It contains servers used only by trusted internal users
    - c. It typically includes an email or web server
    - d. It provides an extra degree of security

12. Which is NOT a type of web filtering scanning?
    - a. Cloud scanning
    - b. Decentralized proxy scanning
    - c. Agent-based scanning
    - d. Browser scanning

13. Which is NOT infrastructure security hardware for protecting a network?
    - a. IPS
    - b. Proxy server
    - c. NGFW
    - d. Switch

14. Which is NOT software-based security protection for infrastructure?
    - a. DNS filtering
    - b. Web filtering
    - c. FIM
    - d. RDR

15. Which device intercepts internal user requests and processes them on behalf of users?
    - a. Intrusion prevention device
    - b. Forward proxy server
    - c. Reverse proxy server
    - d. Host detection server

16. Oda needs to configure VPN to preserve bandwidth. Which configuration would she choose?
    - a. Narrow tunnel
    - b. Wide tunnel
    - c. Split tunnel
    - d. Full tunnel

17. Which is NOT a common network device that can be configured for security?
    - a. Router
    - b. Switch
    - c. Endpoint
    - d. Server

18. Which is found on live production systems?
    - a. Honeyhome
    - b. Honeypot
    - c. Honeynet
    - d. Honeytoken

19. Which is NOT used to create a web filtering block rule?
    - a. Reputation score
    - b. URL scanning
    - c. DNS polling
    - d. Content categorization

20. What is the advantage of XDR over EDR?
    - a. XDR collects and correlates data across various network appliances
    - b. XDR is faster than EDR
    - c. The agent footprint of XDR is significantly smaller
    - d. XDR does not require user input
