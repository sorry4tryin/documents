---
created: 2026-08-19 20:12:00
class:
  - document
description: CompTIA Security+ SY0-701 Module 2 — social engineering, physical security, and data controls
mod.: 2026-08-19 20:12:00
aliases:
  - security+ module 2
  - pervasive attack surfaces
tags:
  - study/security-plus
  - study/security-plus/module-2
---

# Module 2 - Pervasive Attack Surfaces and Controls

## Objectives

1. [[#Objective 1 - Social Engineering Attacks|Define social engineering and list types of attacks]]
2. [[#Objective 2 - Physical Security Controls|List different types of physical defenses]]
3. [[#Objective 3 - Data Controls|Describe controls for protecting data]]

---

## Objective 1 - Social Engineering Attacks

### Examples of Human Manipulation
- **Social engineering**: means of eliciting information or convincing a user to take action that weakens security; almost always performed through deception and manipulation
- Cybercriminals use social engineering in an estimated **98 percent** of their attacks
- Social engineering relies on **human psychology** — attackers use basic principles of psychology to persuade targets to provide information or take actions without realizing they are being taken advantage of

#### Principles of Human Manipulation

| Principle | Description | Example |
|-----------|-------------|---------|
| **Authority** | Directed by someone impersonating authority figure or falsely citing their authority | "I'm the CEO calling." |
| **Intimidation** | To frighten and coerce by threat | "If you don't reset my password, I will call your supervisor." |
| **Consensus** | Influenced by what others do | "I called last week, and your colleague reset my password." |
| **Scarcity** | Something is in short supply | "I can't waste time here." |
| **Urgency** | Immediate action is needed | "My meeting with the board starts in 5 minutes." |
| **Familiarity** | Victim is well known and well received | "I remember reading a good evaluation on you." |
| **Trust** | Confidence | "You know who I am." |

- **Prepending**: influencing the subject before the event occurs; e.g., including urgency with prepended desired outcome

#### Personal Techniques for Gaining Trust
- **Provide a reason**: adding rationalization with the word "because" increases likelihood of compliance
- **Project confidence**: walking calmly through restricted areas without looking at signs or labels
- **Evasion and diversion**: giving vague or irrelevant answers when challenged; feigning innocence or confusion
- **Make them laugh**: humor puts people at ease and develops trust

### Types of Social Engineering Attacks

#### Phishing
- **Phishing**: sending an email or displaying a web announcement that falsely claims to be from a legitimate source to trick the user into taking an action
- Users are asked to respond to an email or directed to a website to update personal information (passwords, credit card numbers, SSNs)
- Phishing emails can also be used to **validate email addresses** through embedded images with unique tracking codes
- Phishing is considered one of the largest and most consequential cyber threats; over **1.2 million phishing attacks** in Q3 2022 alone

##### Phishing Variations

| Variation | Description |
|-----------|-------------|
| **Spear phishing** | Targets specific users; emails customized to the recipient with names and personal information |
| **Whaling** | Targets "big fish" — wealthy individuals or senior executives with larger sums of money |
| **Vishing** | Voice phishing — uses telephone calls with recorded messages pretending to be from legitimate companies |
| **Smishing** | Uses SMS text messages to send fraudulent messages; often combined with callback phone numbers |

#### Business Email Compromise (BEC)
- Takes advantage of common practice of electronically making payments or transferring funds
- Attackers exploit the size and complexity of large enterprises to request funds from legitimate-seeming sources

| BEC Attack | Description |
|------------|-------------|
| **Bogus invoice** | Attacker poses as legitimate supplier and sends fake invoice demanding immediate payment |
| **Executive fraud** | Attacker poses as company executive and tells Finance to transfer funds for unpublicized initiative |
| **Account compromise** | Finance employee's email is compromised and vendors are sent payment demands for fictitious services |

#### Impersonation
- **Impersonation**: masquerading as a real or fictitious character and playing out that role on a target
- **Pretexting**: obtaining private information through impersonation
- Common impersonated roles: repairperson, IT support, manager, trusted third party
- **Brand impersonation**: pretending to be a well-known brand to build immediate recognition and trust

#### Redirection

| Technique | Description |
|-----------|-------------|
| **Typo squatting** | Attacker registers domain names spelled similarly to actual sites to capture users who make typing errors |
| **Bitsquatting** | Registering domain names that are one bit different from actual domains (RAM memory bit-flipping) |
| **Pharming** | Exploiting URL-to-IP address conversion; installing malware on user's computer or infecting a DNS to redirect users to fake sites |

- Over **1,239 generic TLDs** exist today, making it difficult for organizations to register all close-sounding domain names
- One squatting detector found **13,857 typo-squatting domains** registered in a single month

#### Misinformation and Disinformation
- **Misinformation**: false or inaccurate information regardless of intent to mislead
- **Disinformation**: false or inaccurate information from malicious intent — knowingly false and intentionally spread
- Example: hoaxes claiming a "deadly virus" is circulating, instructing users to change configurations or erase files

#### Watering Hole Attack
- Directed toward a smaller group of specific individuals who visit a common website
- Attacker determines the common website, infects it with malware that reaches the target group's computers

#### Data Reconnaissance
- **Dumpster diving**: digging through trash to find useful information (calendars, memos, organizational charts, policy manuals)
- **Google dorking**: using advanced Google search techniques to find documents and data posted online by unsuspecting victims
- **Shoulder surfing**: observing individuals entering access codes, passwords, or PINs; can use binoculars or cameras

---

## Objective 2 - Physical Security Controls

### Perimeter Defenses

#### Barriers
- **Fencing**: tall, permanent structure with signage and lighting; standard chain-link offers limited security
- **Bollard**: short but sturdy vertical post used as vehicular traffic barricade to prevent "ramming" into secure areas
- **Barricade**: designed to block passage of traffic; used for directing large crowds

| Fencing Deterrent | Description | Comments |
|-------------------|-------------|----------|
| **Anticlimb paint** | Nontoxic petroleum gel-based paint that does not harden | Used on poles, downpipes, wall tops above head height |
| **Anticlimb collar** | Spiked collar extending horizontally from pole | Protects equipment mounted on poles |
| **Roller barrier** | Independently rotating large cups on fence top | Prevents gripping; used around public grounds |
| **Rotating spikes** | Tri-wing spike collars rotating around central spindle | Designed for high-security areas |

#### Security Guards
- **Active security defense** — can differentiate between intruder and legitimate visitor and make split-second decisions
- **Two-person integrity/control**: using two guards to prevent one compromised guard from participating in an attack
- Guards monitor **CCTV** (closed-circuit television) — fixed cameras, dome cameras, AI-powered cameras
- **UAVs** (unmanned aerial vehicles/drones) increasingly used for monitoring activity

#### Sensors

| Sensor Type | Description | Best Use |
|-------------|-------------|----------|
| **Infrared (IR)** — Active | Emits and detects IR radiation using LED and receiver; acts as proximity sensor | Determining how close an object is |
| **Infrared (IR)** — Passive | Detects IR radiation from objects; all living beings emit heat giving off IR radiation | Motion-based detection for unauthorized entry |
| **Microwave** | Uses high-frequency radio waves; functions like radar; projects in 360 degrees | Monitoring large areas like warehouses |
| **Ultrasonic** | Transmits waves that bounce off target; converts to electrical signal; Distance = ½ × Time × 343 | Proximity sensors; less susceptible to smoke/gas interference |
| **Pressure** | Detects force exerted on surface per unit area; can differentiate between types of targets (pedestrian, car, truck) | Underground detection with direction tracking |

#### Security Buffers

| Level | Buffer Type | Description |
|-------|------------|-------------|
| **High security** | Access control vestibule (mantrap) | Automated device controls two interlocking doors; only one door can be open at a time |
| **Medium security** | Reception area | Users can enter; receptionist checks credentials; additional precautions needed |
| **Low security** | Waiting room | Check-in window; individuals approved before passing to next area |

#### Locks
- Key-based locks can be compromised if keys are lost, stolen, or duplicated
- **Electronic lock**: uses buttons pushed in proper sequence; can be programmed for time-based access and maintains activity records
- **Smart lock**: uses smartphone that sends code via wireless Bluetooth to open door

### Preventing Data Leakage

#### Faraday Cage
- **Faraday cage**: metallic enclosure that prevents entry or escape of electromagnetic fields
- Consists of grounded, fine-mesh copper screening
- **Faraday bags**: lightweight, portable shields for portable devices
- Often used in crime scene investigations to prevent remote wiping of evidence

#### Protected Distribution System (PDS)
- System of cable conduits used to protect classified information transmitted between two secure areas
- Created by U.S. Department of Defense (DoD)

| PDS Type | Description |
|----------|-------------|
| **Hardened carrier PDS** | Data cables in conduit of electrical metallic tubing; connections permanently sealed; buried conduits encased in concrete; requires regular visual inspection |
| **Alarmed carrier PDS** | Specialized optical fibers sense acoustic vibrations from intrusion attempts; provides continuous monitoring; can be hidden above ceiling or below floor |

### Computer Hardware Security
- **Cable lock**: inserted into security slot of portable device and connected to immovable object
- **Safe/vault**: ruggedized steel box with lock; sizes range from single laptop to multiple devices
- Some safes are prewired for electrical power and network connections for charging and updates

---

## Objective 3 - Data Controls

### Data Classifications

| Data Type | Description | Recommended Handling |
|-----------|-------------|---------------------|
| **Confidential** | Highest level of data sensitivity | Only available to users with highest level of preapproved authentication |
| **Private** | Restricted data with medium level of confidentiality | For users with need-to-know basis |
| **Sensitive** | Data that could cause catastrophic harm if disclosed | Restricted to approved employees with business need |
| **Critical** | Data classified by availability needs; function/mission severely impacted if unavailable | Must be rigorously protected |
| **Public** | No risk of release | For all public consumption |
| **Restricted** | Not available to public | Caution before using in emails |

- Government classifications: top secret, secret, confidential (based on damage to national security)
- No universal agreement on data classifications — entities use 3 to 5+ types

### Types of Data

| Data Type | Description |
|-----------|-------------|
| **Regulated** | External stipulations on who can see/use data; e.g., PHI regulated by HIPAA |
| **Intellectual property (IP)** | Invention or creative work; protected by patent, trademark, copyright, or trade secret |
| **Trade secret** | Undisclosed enterprise data with three required elements: economic value from secrecy, value to others, and reasonable efforts to maintain secrecy |
| **Legal information** | General factual information about law and legal process (different from legal advice) |
| **Financial data** | Monetary transactions — credit card numbers, credit ratings, financial statements, payment histories |
| **Human-readable** | Data a person can read and interpret |
| **Non-human-readable** | Machine-readable data; e.g., JSON (JavaScript Object Notation), XML |

### Data Breach Consequences
- **Reputation damage**: bad publicity results in customer loss and stock price drops; organizations required to send data breach notification letters
- **IP theft**: theft of intellectual property owned by organization or customers
- **Fines**: financial penalties from federal/state laws (HIPAA, Sarbanes-Oxley, GLBA, PCI DSS, GDPR)
  - GDPR first tier: up to 10 million euros or 2% of worldwide annual revenue
  - GDPR second tier: 20 million euros or 4% of worldwide annual revenue
  - HIPAA: breaches of 500+ records reported within 60 days; fewer than 500 reported within 60 days of calendar year end

### Protecting Data

#### Data States

| State | Description |
|-------|-------------|
| **Data in use (processing)** | Data on which actions are being performed by devices |
| **Data in transit (motion)** | Data being transmitted across a network |
| **Data at rest** | Data stored on electronic media |

#### Data Location
- **Geolocation**: techniques that identify data's location using latitude and longitude coordinates
- **GeoIP**: uses IP address of device to determine location (city, state)
- **Data sovereignty**: country-specific requirements that apply to data; generally data is subject to laws of country where collected/processed; many countries require data stored on physical servers within borders (Russia, China, Germany, France, Indonesia, Vietnam)

#### Data Security Methods

| Method | Description |
|--------|-------------|
| **Data minimization** | Limiting collection of personal information to what is directly relevant and necessary |
| **Data masking** | Creating a copy of original data with obfuscation of sensitive elements; irreversible (data sanitization) |
| **Tokenization** | Obfuscating sensitive data into random string of characters (token); original stored in token vault; reversible (pseudo-anonymization) |
| **Permission restrictions** | Limiting individuals and devices to those with legitimate business need |
| **Geographic restrictions** | Limiting data access to specific locations (e.g., HIPAA data only on hospital campus) |
| **Data segmentation** | Identifying classification, tagging data elements, separating most sensitive data as "protect surface" with additional security measures |

---

## Key Terms

- **Access control vestibule** — automated device with two interlocking doors; only one door open at a time
- **Brand impersonation** — pretending to be a well-known brand to build immediate recognition and trust
- **Business email compromise (BEC)** — attack taking advantage of electronic payments and fund transfers
- **Confidential** — highest level of data sensitivity
- **Critical** — data whose unavailability severely impacts function and mission
- **Data at rest** — data stored on electronic media
- **Data classifications** — categories for grouping data by sensitivity and required protection
- **Data in transit** — data being transmitted across a network
- **Data in use** — data on which actions are being performed
- **Data sanitization** — process of cleaning data for privacy protection
- **Data sovereignty** — country-specific requirements that apply to data
- **Disinformation** — false information from malicious intent, knowingly spread
- **Geolocation** — techniques identifying data's location
- **Impersonation** — masquerading as a real or fictitious character on a target
- **Infrared (IR) sensor** — electronic device detecting IR in surrounding area
- **Intellectual property (IP) data** — invention or creative work protected by law
- **Microwave sensor** — uses high-frequency radio waves like radar for monitoring large areas
- **Misinformation** — false or inaccurate information regardless of intent
- **Phishing** — email or web announcement falsely claiming legitimate source to trick user
- **Pretexting** — obtaining private information through impersonation
- **Private** — restricted data with medium confidentiality
- **Regulated data** — data with external stipulations on access and use
- **Restricted** — data not available to public
- **Segmentation** — separating most sensitive data with additional security layers
- **Sensitive** — data that could cause catastrophic harm if disclosed
- **Social engineering** — eliciting information or convincing user to take weakening action
- **Smishing** — social engineering via SMS text messages
- **Tokenization** — obfuscating sensitive data into random tokens
- **Trade secret** — undisclosed enterprise data with economic value from secrecy
- **Typo squatting** — registering domains spelled similarly to actual sites
- **Ultrasonic sensor** — measures distance using sound waves bounced off targets
- **Vishing** — voice phishing via telephone calls
- **Watering hole attack** — infecting a common website frequented by target group

---

## Review Questions

1. What is the attack surface of social engineering?
   - a. Manipulation
   - b. Human vectors
   - c. Persuasion
   - d. Deception

2. Bjorn received a phone call from someone claiming to be a senior vice president demanding his password be reset, or else his supervisor would be contacted. Which principle of human manipulation did the attacker attempt?
   - a. Authority
   - b. Fright
   - c. Intimidation
   - d. Urgency

3. Which of the following is NOT a personal technique used by social engineering attackers to gain trust?
   - a. Provide a reason
   - b. Project confidence
   - c. Demand compliance
   - d. Use evasion and diversion

4. Albrecht received a call from a senior vice president of finance who had received a phishing email and had deleted it. What type of phishing attack was this?
   - a. Dolphining
   - b. Harpooning
   - c. Phishing spear
   - d. Whaling

5. Tobias received an SMS text message falsely saying his bank account was overdrawn and he should contact the bank immediately. What type of attack is this?
   - a. Texting attack
   - b. SMS phishing
   - c. Smishing
   - d. IM vectoring

6. Which of the following is NOT true about BEC?
   - a. It is decreasing in popularity among threat actors
   - b. It takes advantage of electronically making payments or transferring funds
   - c. It takes advantage of the size and complexity of large enterprises
   - d. It is not limited to businesses

7. Which social engineering attack is masquerading as a real or fictitious character and playing out that role on a target?
   - a. Pretending
   - b. Pretexting
   - c. Impersonation
   - d. Acting

8. Wolfgang-Cashman is researching all similar domain names to his company's website. What is he combating?
   - a. Mistranslations
   - b. Spimming
   - c. Typo squatting
   - d. Redactioning

9. What is false or inaccurate information that comes from a malicious intent?
   - a. Misinformation
   - b. Half-truths
   - c. Disinformation
   - d. Varication

10. Which of the following is NOT a type of data reconnaissance?
    - a. Purchasing used technology equipment
    - b. Excel dorking
    - c. Dumpster diving
    - d. Shoulder surfing

11. Which type of sensor is most appropriate for monitoring a large warehouse for intruders?
    - a. Microwave sensor
    - b. IR sensor
    - c. XG sensor
    - d. Passive RGP sensor

12. Which of the following is NOT true about a pressure sensor?
    - a. A pressure sensor can differentiate between a car and a person
    - b. Modern pressure sensors can differentiate between what has entered and where they are headed
    - c. A pressure sensor is a type of management control
    - d. A pressure sensor can detect if a person has entered a restricted area

13. Which sensor would alarm whenever someone gets too close to a door while allowing others to pass?
    - a. IR sensor
    - b. Microwave sensor
    - c. Ultrasonic sensor
    - d. Pressure sensor

14. Which type of buffer is automated and has two interlocking doors, only one of which can be opened at a time?
    - a. Access control vestibule
    - b. Reception area
    - c. Waiting room
    - d. Vestibule office

15. What requirement would be added to specifications for a hardened carrier PDS running underground between two buildings?
    - a. It must be buried at least 25 feet below surface level
    - b. It can only be used for fiber-optic cables
    - c. It must be visually inspected on a weekly basis
    - d. It must be encased in concrete

16. Which data classification has the highest level of data sensitivity?
    - a. "Eyes-only"
    - b. Sensitive
    - c. Private
    - d. Confidential

17. If compromised, data whose unavailability would severely impact the function and mission of the enterprise should be classified as:
    - a. Secret
    - b. Top secret
    - c. Critical
    - d. Classified

18. Hospital patient information protected by HIPAA is which type of data?
    - a. Restricted data
    - b. Regulated data
    - c. Secure data
    - d. Private data

19. JSON and XML would be classified as which type of data?
    - a. Compiled data
    - b. Lightweight data
    - c. Schematic data
    - d. Non-human-readable data

20. Which data security method creates a copy of the original data but uses obfuscation on sensitive elements?
    - a. Data masking
    - b. Data protecting
    - c. Data tokening
    - d. Data covering
