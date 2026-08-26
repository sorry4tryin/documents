---
created: 2026-08-25 20:15:00
class:
  - document
description: CompTIA Security+ SY0-701 Module 13 — preparatory plans, resilience through redundancy, and incident investigation
mod.: 2026-08-25 20:15:00
aliases:
  - security+ module 13
  - incident preparation
tags:
  - study/security-plus
  - study/security-plus/module-13
---

# Module 13 - Incident Preparation and Investigation

## Objectives

1. [[#Objective 1 - Preparatory Plans|Explain how to prepare for a cyber incident]]
2. [[#Objective 2 - Resilience Through Redundancy|Describe how to achieve resilience through redundancy]]
3. [[#Objective 3 - Incident Investigation|Describe how to conduct an analysis of an incident]]

---

## Objective 1 - Preparatory Plans

### Business Continuity Planning

#### Business Continuity Plan (BCP)
- **Business continuity**: ability of an organization to maintain operations and services in the face of a disruptive event or major disaster
- Disasters: environmental (floods, hurricanes, tornados), human-made (industrial mishaps, chemical spills, terrorist attacks), cyberattack
- **Business continuity planning (BCP)**: process undertaken in advance to determine a plan of action to protect the organization in the event of a disaster
- **Business continuity plan (BCP)**: strategic document providing alternative modes of operation for business activities that, if interrupted, could result in a significant loss
- Creating a BCP: identifying exposure to threats, creating preventive and recovery procedures, testing them
- BCP may also include **succession planning** (who takes over in event of incapacitation of key employees)

##### Elements of a BCP
- **High availability**: ability to withstand all outages (planned and unplanned) while providing continuous processing for critical applications
  - Example: fully automated failover to backup system for critical e-commerce servers
- **Scalability**: BCP must have the capability to cover increased capacity as organization grows
- **Diversity**: must include diversity as different technologies, third-party vendors, controls, and cryptographic solutions are added
- **On-prem and cloud**: flexibility to address movement of resources from on-premises to cloud

##### Continuity of Operations Planning (COOP)
- Federal initiative encouraging organizations to address how critical operations will continue under a broad range of negative circumstances
- Addresses emergencies from an "all-hazards approach" instead of focusing narrowly on a specific event
- Designed to establish requirements for ensuring critical functions continue
- Includes how personnel and resources can be relocated in case of emergencies

#### Business Impact Analysis (BIA)
- **Business impact analysis (BIA)**: identifies business processes and functions, then quantifies the impact a loss of these functions may have on business operations
- Impacts include: property (tangible assets), finance (monetary funding), safety (physical protection), reputation (status), life (well-being)
- **Site risk assessment**: detailed evaluation of processes performed at a site and how they can be impacted
- BIA identifies **mission-essential function** (core purpose of the enterprise)
  - Example: hospital → "Deliver healthcare services to individuals and their families"
- Identifies **critical systems** that support the mission-essential function
- Identifies **single point of failure**: component or entity that, if it no longer functions, will disable the entire system

##### Percentage Availability and Downtimes

| Percentage Availability | Name | Weekly Downtime | Monthly Downtime | Yearly Downtime |
|---|---|---|---|---|
| 90% | One Nine | 16.8 hours | 72 hours | 36.5 days |
| 99% | Two Nines | 1.68 hours | 7.20 hours | 3.65 days |
| 99.9% | Three Nines | 10.1 minutes | 43.2 minutes | 8.76 hours |
| 99.99% | Four Nines | 1.01 minutes | 4.32 minutes | 52.56 minutes |
| 99.999% | Five Nines | 6.05 seconds | 25.9 seconds | 5.26 minutes |
| 99.9999% | Six Nines | 0.605 second | 2.59 seconds | 31.5 seconds |

- Many BIAs also contain a **privacy impact assessment** to identify and mitigate privacy risks (PII examination)

#### Disaster Recovery Plan (DRP)
- **Disaster recovery plan (DRP)**: written document detailing the process for restoring IT functions and services following a significant disruption
- Subset of BCP focused on IT continuity
- Comprehensive in scope; updated regularly
- Common topic: **restoration order** (sequence in which systems are reinstated)
  - Factors: obvious dependencies, critical systems supporting mission-essential function, alternative business practices (workaround activities)

### Incident Response Planning

#### Creating an Incident Response Plan
- **Incident response plan**: set of written instructions for reacting to an information security incident

##### Incident Response Process

| Action Step | Description |
|---|---|
| **Preparation** | Equipping IT staff, management, and users to handle potential incidents |
| **Detection** | Determining whether an event is actually a security incident |
| **Analysis** | Collecting data from tools and systems to identify indicators of compromise |
| **Containment** | Limiting damage and isolating impacted systems to prevent further damage |
| **Eradication** | Finding the cause and temporarily removing systems causing damage |
| **Recovery** | After ensuring no threat remains, permitting affected systems to return to normal |
| **Lessons learned** | Completing incident documentation, performing detailed analysis, improving future response |

##### Additional Plan Elements
- **Definitions**: clear descriptions of types and categories of documented incidents
- **Incident response team**: responsible for responding to security incidents; includes technical specialists, public-relations employees, managers; each member has clearly designated duties
- **Reporting requirements**: to whom information should be distributed; includes **stakeholder management** (operations, legal, technical, finance, human resources)

### Performing Testing Exercises

| Exercise | Description | Example |
|---|---|---|
| **Tabletop** | Monthly 30-minute discussion of a scenario in informal/stress-free environment | Vendor-provided USB drives on conference table that weren't actually provided by vendor |
| **Walkthrough** | IT personnel review plan steps, focusing on IT systems/services that may be targeted | Technician walks through proposed recovery procedures to find omissions/gaps/errors |
| **Simulation** | Hands-on exercise using realistic scenario to thoroughly test each step | Senior VP opens malicious attachment introducing malware |
| **Fail over** | Testing process of temporarily switching to backup procedures after attack | Server connection terminated to test backup server takeover |
| **Parallel processing** | Conducting same tests simultaneously in multiple environments | Firewall attack test at main campus also conducted at remote site |

### Studying Attack Frameworks
- **Information security framework**: series of documented processes defining policies/procedures for security controls
- **Exploitation frameworks**: models of thinking and actions of threat actors

#### MITRE ATT&CK
- Knowledge base of attacker techniques broken down and classified in detail
- Offensively oriented actions against particular platforms
- Focus: how attackers interact with systems during an operation (not tools/malware used)
- Techniques arranged into tactics for context

#### Diamond Model of Intrusion Analysis
- Framework for examining network intrusion events
- Four core interconnected elements: **adversary**, **infrastructure**, **capability**, **victim**
- Analyzing incidents involves piecing together the Diamond using information from these four facets

#### Cyber Kill Chain
- Military term adapted for cyber: systematic process to target and engage an enemy
- Introduced by Lockheed Martin in 2011

| Step | Description |
|---|---|
| **Reconnaissance** | Harvest email addresses, company information, etc. |
| **Weaponization** | Couple exploit with backdoor into deliverable payload |
| **Delivery** | Deliver weaponized bundle to victim via email, web, USB, etc. |
| **Exploitation** | Exploit vulnerability to execute code on victim system |
| **Installation** | Install malware on the asset |
| **Command & Control** | Command channel for remote manipulation of victim |
| **Actions on Objectives** | With "Hands on Keyboard" access, accomplish original goal |

- Disrupting any step interrupts the entire attack; disrupting early steps is most effective and least costly

---

## Objective 2 - Resilience Through Redundancy

### Capacity Planning
- **Capacity planning**: process of forecasting need for future resources by analyzing maximum capacity of current environment
- Three types: **people capacity planning**, **technology capacity planning**, **infrastructure capacity planning**
- Designed to prevent **overprovisioning** (too many underutilized resources) and **underprovisioning** (too few resources)
- Some excess capacity is intentional — **platform diversity** (using multiple different devices to host/serve an application)

### Equipment Redundancy
- **Redundancy** (extra components not strictly necessary) provides **resilience** (elasticity or flexibility)
- Goal: reduce **mean time to recovery**; some systems designed to have mean value of zero (redundant components take over instantly)

### Servers
- Loss of one or more servers supporting critical application has significant impact
- **Server cluster**: combination of two or more servers interconnected to appear as one
  - Connected through **public cluster connection** (clients see single unit) and **private cluster connection** (servers exchange data)

| Cluster Type | Description |
|---|---|
| **Asymmetric server cluster** | Standby server exists only to take over if another server fails; performs no useful work |
| **Symmetric server cluster** | Every server performs useful work; if one fails, remaining servers perform their normal work plus that of the failed server |

- Virtualization has reduced need for physical server clusters; VMs can be quickly moved to another physical server

### Drives

#### Types of Drives
- **Hard disk drives (HDDs)**: spinning platters, actuator arms with read/write heads; mainstay for 40+ years
- **Solid-state drives (SSDs)**: store data on chips; more resistant to failure, more reliable than HDDs
- Most servers use both: boot from SSD (speed/reliability), store data on HDD (lower cost)
- **Mean time to repair (MTTR)**: average time to restore failed component to working order — meaningless for drives (can't repair)
- **Mean time between failures (MTBF)**: average time until a component fails and must be replaced
  - Used to determine number of spare drives needed

#### RAID
- **RAID** (Redundant Array of Independent/Inexpensive Drives): uses multiple hard drives for increased reliability and performance
- Can be implemented through **software** (OS level) or **hardware** (specialized controller)
- Supports multiple HDDs or SSDs

| RAID Level | Name | Description |
|---|---|---|
| **RAID 0** | Striped disk array without fault tolerance | Partitions drives into stripes; data alternated across drives; NOT fault-tolerant |
| **RAID 1** | Mirroring | Multiple drives connected to same controller; each write sent to each drive; exact duplicates; **disk duplexing** = separate controller cards per drive |
| **RAID 5** | Independent disks with distributed parity | Parity data distributed across all drives; data on one drive, parity on another |
| **RAID 10** | Nested (RAID 0 + RAID 1) | Combination of striping and mirroring |

| Use Case | Recommended Level |
|---|---|
| Noncritical high-speed storage (image/video editing) | RAID 0 |
| Mission-critical storage (accounting systems, small servers) | RAID 1 |
| File/app servers with limited data drives | RAID 5 |

- RAID is NOT intended to replace data backups

### SAN Multipath
- **Storage area network (SAN)**: dedicated network storage facility providing access over high-speed network; consolidates storage as single pool
- **SAN multipath**: more than one physical path between devices and a SAN; if one path interrupted, redirects to another; also assists with speed by spreading connections

### Networks
- Redundant networks wait in background during normal operations; use replication to keep copy current
- If disaster occurs, redundant network launches automatically (transparent to users)
- **NIC teaming**: up to 32 physical adapters configured into software-based virtual network adapters
- Some switches/routers have primary active port + standby failover port
- **SDN controllers** can increase reliability by setting up multiple paths between origin and destination

### Power
- Critical devices fitted with **dual power supply** (if one fails, other takes over)
- **Managed power distribution unit (PDU)**: distributes electric power to racks of computers/networking equipment
- **Uninterruptible power supply (UPS)**: maintains power during interruption; more than a big battery

| UPS Type | Description |
|---|---|
| **Off-line UPS** | Least expensive; equipment served by primary power source normally; switches to battery within milliseconds if power interrupted |
| **On-line UPS** | Always running off battery; main power runs charger; not affected by voltage dips/sags; cleans electrical power; serves as surge protector |

- **Backup generators**: diesel, natural gas, or propane; permanently installed; automatic transfer switches

### Sites

| Site Type | Description |
|---|---|
| **Hot site** | Duplicate of production site; all equipment, office space, telecom link; data can be moved within an hour |
| **Cold site** | Office space only; customer must provide/install equipment; no data backups immediately available; less expensive |
| **Warm site** | Equipment installed but no active Internet/telecom; no current backups; up to half a day to activate |

- **Geographic dispersal**: sites distributed across larger area to mitigate impact of disasters

### Clouds
- Two considerations for cloud resilience:
  1. **Location of data** — geographic dispersal through **high availability across zones**
  2. **Multicloud systems** — spread across multiple cloud providers; tolerates critical issue with single provider

### Data

#### Data Copy Calculations
- **Recovery point objective (RPO)**: maximum length of time organization can tolerate between copies; "age" of data to restore
  - Example: RPO of one hour → make copies at least every hour
- **Recovery time objective (RTO)**: length of time to recover copied data
  - Example: RTO of 10 minutes → data restored within that timeframe

#### Backups vs. Replication

| Characteristic | Backup | Replication |
|---|---|---|
| **Description** | Single scheduled event; data copied and stored | Continuously copies data; duplicated across multiple sites |
| **Purpose** | Long-term archival of business records | Quickly restore corrupted data |
| **Use case** | All enterprise devices from endpoints to servers | Mission-critical applications that must always be available |
| **Technology** | Specialized backup software | Snapshots or journaling |
| **Recovery time** | Long | Immediate |
| **Cost** | Relatively inexpensive | Sizeable investment in infrastructure |

- **Snapshot**: takes "picture" of data state repeatedly; restore from specific point in time
- **Journaling**: makes copy of data whenever a change occurs
- **3-2-1 backup plan**: maintain three copies, two different types of media, one offsite

---

## Objective 3 - Incident Investigation

### Root-Cause Analysis
- **Root-cause analysis (RCA)**: process of discovering the origin (root) cause of the security event
- Must examine not just results or what threat actors did, but dig to the origin

### Data Sources

#### Log Files
- **Log**: record of events that occur

| Log Type | Description |
|---|---|
| **Firewall logs** | Determine if new IP addresses probing network; outgoing/incoming/denied/permitted connections |
| **IDS/IPS logs** | Detailed security log on suspicious behavior and attacks; record IPS actions taken |
| **Application logs** | Information about attacks on different apps; can create **dump file** (snapshot of executing process and loaded modules) |
| **Endpoint logs** | Wide range of reports/alerts: system events, software installations, removable disk activity, Registry changes, login/session activity |
| **OS-specific security logs** | System events (operational actions), audit records (authentication attempts, file accesses, policy changes, account creation/deletion) |
| **Network logs** | Router and switch logs providing general network traffic information |
| **Metadata logs** | "Data about data" — describes information about other data |

##### Log Management Challenges
- Multiple devices generate logs (each interprets events differently)
- Very large volume of data (many devices record all events, not just security-related)
- Different log formats (different devices record in different formats with different data)

#### Other Data Sources
- Vulnerability scan data
- **SIEM** (security information and event management) dashboards: alerts, trends, sensitivity, correlation data
- Network IP monitors: automated reports on activity
  - **NetFlow**: session sampling on Cisco routers; collects IP traffic using ICMP Echo requests
  - **sFlow**: packet capture sampling; statistical sampling instead of actual flow
  - **IPFIX**: similar to NetFlow but integrates SNMP information directly

### Digital Forensics
- **Digital forensics**: retrieval of difficult-to-obtain data, usually hidden, altered, or deleted by perpetrator
- Searches for evidence pertaining to cybercrime or damage from cyber incident
- Not the same as **e-discovery**: electronic counterpart of manually sifting through documents in discovery (formal process of exchanging information about witnesses and evidence before trial)

#### Forensics Procedures

##### 1. Secure the Scene
- Document physical surroundings
- Identify and tag all cables connected to device
- Take custody of device and peripherals
- Delay of even a few minutes can allow evidence to be overwritten

##### 2. Preserve the Evidence
- Ensure important proof is not corrupted or destroyed
- Helps mitigate **nonrepudiation** (denial by perpetrator)
- Evidence placed in tagged bags with description, numeric identifier, date, collection location
- Sealed with **tamper-evident seal** (cannot be removed/reapplied without visual evidence)
- May need **legal hold**: data cannot be modified, deleted, erased, or otherwise destroyed

##### 3. Document Chain of Custody
- **Chain of custody**: documents evidence was always under strict control; no unauthorized person could corrupt it
- **Provenance**: documenting evidence from the very beginning
- Includes: serial numbers, who handled systems and for how long, how computer was shipped
- Gaps can result in severe legal consequences (cases dismissed)

##### 4. Examine for Evidence

###### Digital Forensics Tools
- **Mirror-image backup** (bit-stream backup): evidence-grade backup replicating all sectors including hidden data and swap/pagefile
- Standard file copies miss significant data and can taint evidence

| Tool | Description |
|---|---|
| **EnCase** | Common forensic suite with common user interface |
| **FTK Imager** | Common forensic suite |
| **memdump** | Linux utility that "dumps" system memory |
| **WinHex** | Hexadecimal editor for forensics |
| **Autopsy** | Digital forensics platform |
| **Digital forensic workstation** | Computer specially configured for forensics; multiple-gigabit ports, hot-swap bays |

###### Mobile Device Forensics
- Mobile devices can extract: call detail records, GPS data, app data, SMS texts, photos/videos

###### Order of Volatility

| Order | Examples | Description |
|---|---|---|
| 1 | Registers and CPU cache | Extremely volatile; change constantly |
| 2 | Routing tables, ARP cache, process table, kernel statistics, RAM | Change quickly during operation; RAM lost if power lost |
| 3 | Temporary file systems | Not subject to rapid changes as prior elements |
| 4 | Hard drive | Relatively stable |
| 5 | Remote logging and monitoring data | More volatile than hard drive but data on drive is more valuable |
| 6 | Physical configuration and network topology | Not volatile; no significant impact |
| 7 | Archival media | Not volatile |

- **Metadata**: can reveal file type, authorship, edit history, creation/access date/time

##### 5. Generate a Report
- Detailed written description of acquisition and analysis of evidence
- Lists steps taken and evidence uncovered
- Can be automatically generated by forensic suites

---

## Key Terms

- **analysis** — collecting data from tools/systems to identify indicators of compromise
- **application logs** — log files giving information about attacks on different applications
- **automated reports** — reports created without manual data analysis
- **backup** — single scheduled event copying data for disaster use
- **business continuity** — ability to maintain operations in face of disruptive events
- **business continuity plan (BCP)** — strategic document providing alternative modes of operation
- **business impact analysis (BIA)** — identifies processes and quantifies impact of loss
- **capacity planning** — forecasting need for future resources
- **chain of custody** — documents evidence was always under strict control
- **clustering** — combining two or more servers to appear as one
- **cold site** — provides office space but customer must provide equipment
- **containment** — limiting damage and isolating impacted systems
- **continuity of operations** — same as business continuity
- **dashboard** — at-a-glance display of current status
- **detection** — determining whether an event is a security incident
- **digital forensics** — retrieval of hidden/altered/deleted data for evidence
- **disaster recovery plan (DRP)** — document for restoring IT functions/services
- **e-discovery** — electronic sifting through documents for trial preparation
- **endpoint logs** — logs providing reports/alerts for endpoints
- **eradication** — finding cause and removing systems causing damage
- **fail over** — switching to backup procedures after attack
- **firewall logs** — logs recording network traffic filtering events
- **frequency** — how often copies should be performed
- **generator** — device creating electrical power as backup
- **geographic dispersal** — distributing sites across larger area
- **high availability** — ability to withstand all outages while providing continuous processing
- **hot site** — duplicate of production site with all equipment ready
- **incident response process** — action steps taken when incident occurs
- **infrastructure capacity planning** — predicting network size needs
- **intrusion detection systems (IDS)/intrusion prevention systems (IPS) logs** — logs recording suspicious behavior and attack detection
- **journaling** — continuous data copy whenever change occurs
- **legal hold** — data cannot be modified, deleted, or destroyed
- **lessons learned** — completing documentation and improving future response
- **log** — record of events that occur
- **mean time between failures (MTBF)** — average time until component fails and must be replaced
- **mean time to repair (MTTR)** — average time to restore failed component
- **metadata logs** — logs containing data about data
- **multi-cloud systems** — using multiple cloud providers
- **network logs** — logs from routers and switches about network traffic
- **offsite** — backup stored away from production facility
- **onsite** — backup stored where data is actually being used
- **OS-specific security logs** — logs recording system events and audit records
- **packet capture** — recorded copy of packets traversing a network
- **parallel processing** — conducting same tests simultaneously in multiple environments
- **people capacity planning** — predicting future human resource needs
- **platform diversity** — using multiple devices to host/serve an application
- **preparation** — equipping staff to handle potential incidents
- **preservation of evidence** — ensuring proof is not corrupted or destroyed
- **recovery** — permitting affected systems to return to normal operation
- **recovery point objective (RPO)** — maximum time tolerable between copies
- **recovery time objective (RTO)** — time to recover copied data
- **replication** — continuously copying data across multiple sites
- **reporting** — detailed written description of acquisition and analysis
- **root cause analysis (RCA)** — discovering the origin cause of a security event
- **simulation** — hands-on exercise using realistic scenario
- **snapshot** — picture of data state taken repeatedly
- **tabletop** — monthly discussion of scenario in informal environment
- **technology capacity planning** — predicting number of devices needed
- **testing** — verifying plan effectiveness through exercises
- **uninterruptible power supply (UPS)** — device maintaining power during interruption
- **walkthrough** — IT personnel review of plan steps
- **warm site** — equipment installed but no active connections or backups

---

## Review Questions

1. Mary Alice has been asked to help develop an outline of procedures to follow in the event of a major IT incident or an incident that directly impacts IT. What type of planning is this?
   a. Business impact analysis planning
   b. IT contingency planning
   c. Disaster recovery planning ✓
   d. Risk IT planning

2. Which of the following is NOT an element that should be part of a BCP?
   a. High availability
   b. Simplicity ✓
   c. Diversity
   d. Scalability

3. Which of the following is a federal initiative that is designed to encourage organizations to address how critical operations will continue under a broad range of negative circumstances?
   a. COOP ✓
   b. BAIA
   c. MFTF
   d. PRPR

4. Bracha is completing a request for proposal (RFP) to be sent to different vendors. The RFP mandates that the annual downtime be the lowest possible. What name will Bracha include on her RFP?
   a. Zero Nines
   b. Nine Nines
   c. Six Nines ✓
   d. Ninety-Nine Nines

5. Eden is creating an incident response plan. Which process involves completing incident documentation, performing detailed analysis to increase security, and improving future response efforts?
   a. Mission-essential functions
   b. Recovery objectives
   c. Lessons learned ✓
   d. Tactical summary

6. Which of the following is NOT an item that should be included in an incident response plan?
   a. Definitions
   b. Incident response team composition
   c. Reporting requirements
   d. Alternative business practices ✓

7. Hannah is planning incident response testing exercises for the next year. This exercise will be a monthly 30-minute discussion of a scenario conducted in an informal and stress-free environment. What is the name of this exercise?
   a. Simulation
   b. Tabletop ✓
   c. Walkthrough
   d. Relaxed scenario event (RSE)

8. Chaya is helping an intern understand RAID. Which of the following is NOT something that Chaya will say about RAID?
   a. It can be implemented in hardware or software.
   b. Nested levels can combine other RAID levels.
   c. It is designed primarily to back up data. ✓
   d. The most common levels of RAID are Levels 0, 1, 5, 6, and 10.

9. Which of the following frameworks is used for examining network intrusion events?
   a. Attack Network Vector (ANV)
   b. MITRE ATT&CK
   c. Cyber Kill Chain
   d. The Diamond Model of Intrusion Analysis ✓

10. Which of the following is used to provide server redundancy?
    a. Load balancing
    b. Server resource sharing (SRS)
    c. Clustering ✓
    d. Server conflagration

11. What device is always running off its battery while the main power runs the battery charger?
    a. Remote UPS
    b. Backup UPS
    c. Off-line UPS
    d. On-line UPS ✓

12. Which type of site is essentially a duplicate of the production site and has all the equipment needed for an organization to continue running?
    a. Cold site
    b. Warm site
    c. Hot site ✓
    d. Mixed site

13. Emma is reading the documentation for the new UPS that just arrived. Which of the following will the new UPS NOT perform?
    a. Prevent certain applications from launching that will consume too much power. ✓
    b. Disconnect users and shut down the server.
    c. Prevent any new users from logging on.
    d. Notify all users that they must finish their work immediately and log off.

14. What is the definition of RPO?
    a. The maximum length of time that can be tolerated between backups. ✓
    b. Length of time it will take to recover data that has been backed up.
    c. The frequency that data should be backed up.
    d. How a backup utility reads an archive bit.

15. Shai is designing the specifications for a new file server. Which of the following configurations will be the most effective?
    a. Boot from HDD, store data on SSD
    b. Boot from SSD, store data on HDD ✓
    c. Boot from either HDD or SSD, store data on SSD
    d. Boot from either HDD or SSD, store data on HDD

16. Noa is writing an email to her team leader about her concerns that all of the organization's cloud resources are isolated on a single cloud provider. What system is Noa advocating?
    a. Spread-cloud system
    b. Multicloud system ✓
    c. Dispersed-cloud system
    d. Spectrum-cloud system

17. Which type of data copy makes a copy whenever a change to the data occurs?
    a. Disk copy
    b. Backup
    c. Snapshot
    d. Journaling ✓

18. Which of the following is the process of discovering the origin (root) cause of a security event?
    a. TBS
    b. XRX
    c. BGP
    d. RCA ✓

19. Which of the following logs contains data that describes information about other data?
    a. Application log
    b. Network log
    c. Metadata log ✓
    d. Endpoint log

20. Which of the following is NOT true about digital forensics?
    a. Digital forensics is a subset of forensics, which is the application of science to questions that are of interest to the legal profession.
    b. Digital forensics involves the retrieval of difficult-to-obtain data, which is usually hidden, altered, or even deleted by the perpetrator.
    c. Digital forensics is often confused with e-discovery, although they are not the same.
    d. Digital forensics has evolved so that virtually anyone can perform it. ✓
