# Module 1 - Introduction to Information Security

## Objectives

1. [[#Objective 1 - What Is Information Security|Define information security and explain its principles]]
2. [[#Objective 2 - Threat Actors and Their Motivations|Identify threat actors and their motivations]]
3. [[#Objective 3 - How Attacks Occur|Explain how attacks occur, including threat vectors and attack surfaces]]
4. [[#Objective 4 - Information Security Resources|Describe information security resources including frameworks, regulations, and standards]]

---

## Objective 1 - What Is Information Security

### Understanding Security
- **Security**: the necessary steps to protect from harm
- Relationship between security and convenience is **inversely proportional**: as security is increased, convenience is decreased

### Principles of Security
- **CIA Triad** (Confidentiality, Integrity, Availability): three basic security protections extended over information
  - **Confidentiality**: ensures only authorized parties can view the information
  - **Integrity**: ensures information is correct and no unauthorized person or malicious software has altered the data
  - **Availability**: ensures data is accessible to only authorized users and not to unapproved individuals
- **AAA** (Authentication, Authorization, and Accounting): framework for controlling access to computer resources
  - **Authentication**: verifying the identity of a user
  - **Authorization**: granting appropriate access rights
  - **Accounting**: tracking user activities and resource consumption

### Security Controls
- **Security control**: a safeguard employed within an enterprise to protect the CIA of information
- A control attempts to limit the exposure of an asset to a danger
- Four broad categories:
  - **Managerial controls**: administrative methods (policies, procedures)
  - **Operational controls**: processes carried out by people
  - **Technical controls**: hardware/software mechanisms
  - **Physical controls**: tangible protections (locks, fences, guards)
- Six specific types within these categories:
  - **Deterrent controls**: discourage potential attackers
  - **Preventive controls**: stop unauthorized activity before it occurs
  - **Detective controls**: identify unauthorized activity as it occurs
  - **Compensating controls**: alternative measures when primary controls aren't feasible
  - **Corrective controls**: remedy the effects of an incident
  - **Directive controls**: direct behavior toward security compliance

### Cybersecurity versus Information Security
- **Cybersecurity**: range of practices, processes, and technologies to protect devices, networks, and programs that process and store data in electronic form
- **Information security**: protects information essential in an enterprise business environment, in any format (electronic files to paper documents)
- Although often used as synonyms, they are strictly different
- **Information security** is often the more appropriate term since enterprises deal with information in various formats

### Defining Information Security
- Protects the **integrity, confidentiality, and availability** of information through products, people, and procedures on devices that store, manipulate, and transmit information

### Information Security Workforce
- Cyberattacks have grown astronomically
- Global workforce reached all-time high but still has a shortage of millions of cyber professionals
- Two broad categories:
  - **Managerial personnel**: administer and manage plans, policies, and people
  - **Technical personnel**: design, configure, install, and maintain technical security equipment

---

## Objective 2 - Threat Actors and Their Motivations

### Unskilled Attackers
- Download automated attack software from websites
- Use it to break into computers with minimal technical knowledge
- **Level of sophistication/capability**: lowest among all threat actors

### Shadow IT
- Process of bypassing corporate approval for technology purchases
- Employees who purchase unapproved software or hardware can create security vulnerabilities

### Organized Crime
- Close-knit group of highly centralized enterprises set up for engaging in illegal activities
- Run by small number of experienced criminal networks who act as entrepreneurs
- Historically: cargo theft, fraud, robbery, kidnapping, "protection" payments
- Now moving into cyberattacks (less risky, more rewarding)
- **Motivation**: financial gain (earning revenue)

### Insider Threats
- Come from own employees, contractors, and business partners (**insiders**)
- Trusted entities who pose a threat from within
- Hard to recognize because the threat actor is already trusted and the enterprise focuses on watching for outsiders
- Most intellectual property (IP) thefts occur within 30 days of an employee resigning
- **Motivation**: revenge, extortion, coercion

### Hacktivists
- Combination of "hack" and "activism"
- Strongly motivated by **philosophical/political beliefs** (ideology)
- Attacks used to "make a statement" (e.g., defacing websites)
- Today work through **disinformation campaigns** (fake news, conspiracy theories)
- **Motivation**: disruption/chaos (extreme confusion)
- Particularly active during COVID-19 pandemic

### Nation-State Actors
- Government-sponsored attackers for launching cyberattacks against foes
- Targets may be foreign governments or citizens considered hostile
- Most deadly threat actors — target is very specific and attackers keep working until successful
- Highly skilled with enough government resources to breach almost any defense
- Often involved in multiyear intrusion campaigns
- **Advanced Persistent Threats (APTs)**: attacks using innovative tools (advanced) that silently extract data over extended time (persistent)
- **Motivation**: espionage (spying) or war (armed hostile combat)

### Other Threat Actors

| Threat Actor | Description | Motivation |
|-------------|-------------|------------|
| **Competitors** | Attack opponent's system to steal classified information | Steal product research, customer lists for competitive advantage |
| **Brokers** | Sell knowledge of weaknesses to other attackers or governments | Financial gain from selling vulnerabilities |
| **Cyberterrorists** | Attack nation's network/computer infrastructure to cause disruption and panic | Target critical infrastructure (power grids, etc.) |

---

## Objective 3 - How Attacks Occur

### Threat Vectors and Attack Surfaces
- **Attack surface** (also called **threat vector**): a digital platform that threat actors target for exploits

#### Mainstream Attack Surfaces

| Category | Attack Surface | Explanation |
|----------|---------------|-------------|
| Software | **Vulnerable software** | Contains security vulnerabilities; can be client-based or agentless |
| Software | **File-based** | Attacks focus on infecting individual files |
| Software | **Image-based** | Vulnerability permits attack on a copy of all computer contents |
| Hardware | **Unsupported systems/applications** | No longer supported; don't receive security updates |
| Hardware | **Removable devices** | USB flash drives can transfer malware between computers |
| Network | **Unsecure networks** | Wired/wireless networks that can be breached |
| Network | **Open service ports** | Unnecessary ports not disabled can allow access |
| Network | **Default credentials** | Preselected admin accounts with well-known passwords |

#### Specialized Threat Vectors

**Communications** — message-based attacks:
- **Email**: ~94% of all malware delivered through email; trick users to open attachments or click hyperlinks
- **Texts**: SMS/MMS messages containing malicious links
- **Instant messages (IM)**: real-time messages pretending to be from reliable sources
- **Voice calls**: often directed to older users pretending to be from legitimate companies

**Supply Chain**:
- Network moving product from creation to end-user (suppliers → manufacturers → vendors → warehouses → distribution → retailers)
- Global scope makes each link potentially thousands of miles away without direct supervision
- **Supply chain infections**: malware injected during manufacturing, storage, or distribution
- **Hardware supply chain infections**: especially dangerous — users receive infected brand-new devices
- **Software supply chain infections**: attackers target software providers and insert malicious code into updates
- **Managed service providers (MSPs)**: IT service providers who manage networks/computers for SMEs; infected MSP can distribute malware to many clients
- **Open-source software**: ideal for attackers since contributions are rarely vetted

### Categories of Vulnerabilities
- **Vulnerability** (Latin: "wound"): state of being exposed to the possibility of being attacked or harmed

#### Software Vulnerabilities
- **OS-based vulnerabilities**: operating systems are the chief culprit
  - Windows 11: ~50 million lines of code; Linux Debian: 68 million; macOS: up to 86 million
  - MS-DOS v1.0 had only 4,000 lines of code
- **Applications** can also have vulnerabilities
- **Malicious update**: threat actor causes user to download code believed to be a valid update but is actually malicious

#### Hardware Vulnerabilities
- **Difficulty patching firmware**: firmware (embedded software) can be difficult to update; not all can be patched
- **Legacy platforms**: older hardware not updated or replaced; deprived of recent security fixes
- **End-of-life (EOL) hardware**: end of manufacturing lifespan

| EOL Risk | Explanation |
|----------|-------------|
| Lack of security updates | Vulnerabilities won't be patched until device is replaced |
| High maintenance cost | No firmware upgrades, replacement parts unavailable |
| Loss of comprehensive security | Aging hardware fails more frequently, creates security holes |
| Legal implications | May fail to comply with regulatory standards, resulting in fines |

#### Misconfigurations

| Configuration | Explanation | Example |
|--------------|-------------|---------|
| **Default settings** | Predetermined by vendor for usability, not security | Router with default password |
| **Open ports/services** | Devices allow most access for user to close later | Firewall with FTP ports open |
| **Unsecured root accounts** | Root account gives unfettered access | Misconfigured cloud storage |
| **Open permissions** | User access over restricted files | Read/Write/Execute when only Read needed |
| **Unsecure protocols** | Using protocols without adequate protection | Telnet or SNMPv1 |
| **Weak encryption** | Known vulnerable encryption mechanism | Encryption with known weakness or short key |
| **Errors** | Human mistakes selecting wrong settings | Using deprecated settings |

#### Zero-Day Vulnerabilities
- **Zero-day vulnerability**: vulnerability exploited before anyone knows it exists
- Zero days of warning — no security fixes available
- Extremely serious because systems are open to attack
- Google's Project Zero: 14 vulnerabilities in 2014 → 68 in 2021 → 244 total to date

### Impacts of Attacks

#### Data Impacts

| Impact | Description | Example |
|--------|-------------|---------|
| **Data loss** | Destruction of data so it cannot be recovered | Maliciously erasing cancer research patient data |
| **Data exfiltration** | Stealing data to distribute to other parties | Taking customer list and selling to competitor |
| **Data breach** | Stealing data to disclose in unauthorized fashion | Theft of credit card numbers |
| **Identity theft** | Taking PII to impersonate someone | Stealing SSN to secure bank loan in victim's name |

#### Overall Effects
- **Availability loss**: systems inaccessible, lost productivity
- **Financial loss**: impacts normal tasks for generating income
- **Reputation damage**: devastating impact on public perception; customers leave for competitors

---

## Objective 4 - Information Security Resources

### Frameworks
- **Information security framework**: documented processes defining policies/procedures for implementing and managing security controls
- ~84% of U.S. organizations use a security framework; 44% use multiple frameworks
- **NIST** (National Institute of Standards and Technology): most popular frameworks

#### NIST Framework Structure
Three parts:
1. **Framework core**: defines activities needed for cybersecurity results
   - **Functions**: most basic tasks (Identify, Protect, Detect, Respond, Recover)
   - **Categories**: tasks for each function
   - **Subcategories**: tasks/challenges for each category
   - **Information sources**: documents detailing specific tasks
2. **Implementation tiers**: four tiers measuring level of compliance (higher = more compliant)
3. **Profiles**: status of cybersecurity measures and roadmaps toward compliance

#### Two NIST Frameworks
- **NIST Risk Management Framework (RMF)**: comprehensive roadmap integrating cybersecurity, privacy, and supply chain risk management
- **NIST Cybersecurity Framework (CSF)**: measuring stick for comparing cybersecurity practices relative to threats

### Regulations
- **Regulatory compliance**: adhering to industry regulations
- Developed by professional organizations or government agencies
- Organizations face challenges: must follow multiple regulations from different bodies
- Requirements in one regulation may conflict with another

### Legislation
- National, territorial, and state laws providing information security resources
- Often leads to a "hodge-podge" of contradictory legislation
- Example: No federal data breach notification law; each state has different laws (California's Act passed 2003, all states by 2018)

### Standards
- **Standard**: document approved through consensus by a recognized standardization body
- Provides frameworks, rules, guidelines, or characteristics for products
- Compliance is not strictly mandatory but may have restrictions for non-compliance
- Example: **PCI DSS** (Payment Card Industry Data Security Standard) — Requirement 11: "Regularly test security systems and processes"

### Benchmarks/Secure Configuration Guides
- Distributed by hardware manufacturers and software developers
- Guidelines for configuring devices/software to be resilient to attacks
- Platform/vendor-specific guides for network infrastructure, OSs, web servers, application servers

### Information Sources
- **Generic sources**: vendor websites, conferences, academic journals, local industry groups, social media
- **Specialized cybersecurity sources**:
  - **Requests for Comments (RFCs)**: document "white papers" authored by technology body specialists describing methods, behaviors, research, or innovations
  - **Data feeds**: continually maintained databases of latest cybersecurity incidents
    - **Vulnerability feeds**: information on latest vulnerabilities
    - **Threat feeds**: outline current threats and attacks
    - **Adversary TTP** (Tactics, Techniques, and Procedures): database of threat actor behavior

---

## Key Terms

- **Accounting** — tracking user activities and resource consumption
- **Agentless software** — no additional background processes required
- **Applications** — software programs
- **Attack surface (threat vector)** — digital platform targeted by threat actors
- **Authentication** — verifying identity of a user
- **Authentication, Authorization, and Accounting (AAA)** — framework for controlling access
- **Authorization** — granting appropriate access rights
- **Availability** — data accessible to authorized users
- **Blackmail** — extortion using threats
- **Client-based software** — applications installed on networked computers
- **Compensating controls** — alternative measures when primary controls aren't feasible
- **Confidentiality** — only authorized parties can view information
- **Confidentiality, Integrity, Availability (CIA)** — three fundamental security protections
- **Corrective controls** — remedy effects of an incident
- **Data exfiltration** — stealing data to distribute to others
- **Default credentials** — preselected admin accounts with known passwords
- **Detective controls** — identify unauthorized activity
- **Deterrent controls** — discourage potential attackers
- **Directive controls** — direct behavior toward security compliance
- **Disruption/chaos** — motivation of hacktivists
- **End-of-life (EOL)** — end of manufacturing lifespan
- **Espionage** — motivation of nation-state actors (spying)
- **Ethical** — moral principles governing behavior
- **File-based** — attacks targeting individual files
- **Firmware** — software embedded in hardware
- **Financial gain** — motivation of organized crime
- **Hacktivists** — attackers motivated by philosophical/political beliefs
- **Image-based** — attacks on copies of computer contents
- **Insider threat** — threat from trusted internal entities
- **Instant messaging (IM)** — real-time messaging technology
- **Integrity** — data is correct and unaltered
- **Legacy platform** — older hardware not updated/replaced
- **Level of sophistication/capability** — measure of attacker skill
- **Malicious update** — deceptive code disguised as legitimate update
- **Managed service providers (MSPs)** — IT service providers for SMEs
- **Managerial controls** — administrative security methods
- **Message-based** — communication-based attack vectors
- **Misconfigurations** — improperly implemented security settings
- **Nation-state actors** — government-sponsored attackers
- **Open service ports** — unnecessary ports not disabled
- **Operational controls** — processes carried out by people
- **Organized crime** — centralized criminal enterprises
- **OS-based vulnerabilities** — vulnerabilities in operating systems
- **Philosophical/political beliefs** — motivation of hacktivists
- **Physical controls** — tangible security protections
- **Preventive controls** — stop unauthorized activity
- **Revenge** — motivation of insider threats
- **Resources/funding** — attacker capabilities
- **Removable devices** — USB drives and similar media
- **Security control** — safeguard protecting CIA
- **Service disruption** — motivation of cyberterrorists
- **Shadow IT** — bypassing corporate technology approval
- **Short Message Service (SMS)** — text messaging service
- **Software provider** — developer and supplier of software
- **Suppliers** — first step in supply chain
- **Supply chain** — network moving product to end-user
- **Technical controls** — hardware/software security mechanisms
- **Threat actor** — entity that carries out attacks
- **Unsecure networks** — networks vulnerable to breach
- **Unsupported systems** — no longer supported/receiving updates
- **Unskilled attackers** — low-sophistication threat actors
- **Vulnerable software** — software with security weaknesses
- **War** — motivation of nation-state actors
- **Zero-day** — vulnerability with no advance warning

---

## Review Questions

1. Vittoria is working on her computer information systems degree and has started researching information security positions. Because she has no prior experience, which position would she most likely be offered?
   - a. Security administrator
   - b. Security technician
   - c. Security officer
   - d. Security manager

2. Which of the following is false about the CompTIA Security+ certification?
   - a. Security+ is one of the most widely acclaimed security certifications
   - b. Security+ is internationally recognized as validating a foundation level of security skills
   - c. The Security+ certification is a vendor-neutral credential
   - d. Professionals with Security+ earn about the same or slightly less than those without

3. Which statement most accurately indicates the relationship between security and convenience?
   - a. Security and convenience are directly proportional
   - b. Security and convenience have no relationship
   - c. Any proportions depend on the type of attack
   - d. Security and convenience are inversely proportional

4. Which CIA element ensures only authorized parties can view protected information?
   - a. Confidentiality
   - b. Integrity
   - c. Availability
   - d. Credentiality

5. Which AAA element is applied immediately after a user has logged into a computer?
