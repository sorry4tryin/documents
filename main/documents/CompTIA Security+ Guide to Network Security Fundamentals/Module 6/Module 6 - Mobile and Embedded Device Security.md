---
created: 2026-08-20 12:00:00
class:
  - document
description: CompTIA Security+ SY0-701 Module 6 — mobile, embedded, and specialized device security with application security
mod.: 2026-08-20 12:00:00
aliases:
  - security+ module 6
  - mobile and embedded device security
tags:
  - study/security-plus
  - study/security-plus/module-6
---

# Module 6 - Mobile and Embedded Device Security

## Objectives

1. [[#Objective 1 - Mobile Devices|List and compare the different types of mobile devices and their risks]]
2. [[#Objective 2 - Securing Mobile Devices|Explain the ways to secure a mobile device]]
3. [[#Objective 3 - Embedded Systems and Specialized Devices|Describe the vulnerabilities and security considerations of embedded and specialized devices]]
4. [[#Objective 4 - Application Security|Explain how application security can provide protections]]

---

## Objective 1 - Mobile Devices

### Types of Mobile Devices

#### Tablets
- Portable computing devices first introduced in 2010; thinner, lighter, more intuitive than other computers
- Screen sizes: 5–8.5 inches or 8.5–10 inches; weight generally less than 1.5 pounds; less than ½ inch thick
- **Accelerometer**: sensor that senses vibrations/movements to determine device orientation
- Generally lack built-in keyboard/mouse; rely on touch screen gestures
- Popular OSs: Apple iPadOS, Google Android, Microsoft Windows

| Gesture | Action | Usage |
|---------|--------|-------|
| **Tap** | Lightly striking the screen | Make a selection |
| **Double tap** | Two quick taps in succession | Zoom in/out |
| **Flick** | Quickly swipe in desired direction | Scroll or pan quickly |
| **Drag** | Place finger and move in desired direction | Scroll or move viewing area |
| **Pinch open** | Thumb and finger move apart | Zoom in |
| **Pinch close** | Thumb and finger move toward each other | Zoom out |
| **Touch and hold** | Touch screen until action occurs | Display info bubble or magnify |
| **Two-finger scroll** | Move two fingers together in same direction | Scroll content with overflow |

#### Smartphones
- Evolved from feature phones (cameras, MP3 players, text messaging)
- **Smartphone**: touchscreen display, powerful cameras, external storage, OS that allows apps
- Described as "handheld personal computers that also happen to make phone calls"

#### Wearables
- Devices worn by user instead of carried; provide greater flexibility and mobility

| Wearable | Description |
|----------|-------------|
| **Smartwatch** | Receives notifications, manages media, contactless payment, emergency services |
| **Fitness tracker** | Heart rate monitoring, GPS tracking, oxygen consumption, sleep monitoring |

- Many use LED lights for readings: **green LEDs** for exercise (more accurate, higher power), **red LEDs** for resting (less accurate, saves battery)
- **Photoplethysmography (PPG)**: method of measuring heart rate by measuring changes in light absorption

#### Portable Computers
- Devices that closely mirror functionality of standard desktop computers

| Type | Description |
|------|-------------|
| **Laptop** | Replicates desktop abilities; small enough for lap or small table |
| **Notebook** | Smaller, lightweight version of laptop; fits in briefcase |
| **Convertible/2-in-1** | Flexible hinge allows laptop, tablet, stand, or tent configurations |
| **Web-based computer** | Limited OS with web browser; Internet-focused; cannot install traditional software |

### Mobile Device Connectivity Methods

| Method | Description |
|--------|-------------|
| **Cellular** | Network divided into hexagonal cells; each cell has transmitter connected to MTSO (Mobile Telecommunication Switching Office); current technology: 5G |
| **Wi-Fi** | Wireless local area network (WLAN) replacing/supplementing wired LAN |
| **Bluetooth** | Short-range radio frequency transmissions; rapid device pairings |
| **USB connections** | Standard connection type on mobile devices is USB Type-C |

### Enterprise Deployment Models

| Model | Description | Employee Actions | Business Actions |
|-------|-------------|-----------------|-----------------|
| **BYOD (Bring Your Own Device)** | Users use own personal devices for business | Full responsibility for device | Popular with smaller companies/temporary staff |
| **COPE (Corporate Owned, Personally Enabled)** | Employees choose from company-approved devices | Supplied device paid by company; can use for personal activities | Company decides level of choice/freedom |
| **CYOD (Choose Your Own Device)** | Employees choose from limited approved devices | Pay upfront cost; offered company-approved suite | Company provides stipend for monthly fees |
| **Corporate-owned** | Device purchased and owned by enterprise | Use phone only for company business | Enterprise responsible for all aspects |

#### Benefits of BYOD, COPE, CYOD Models
- **Management flexibility**: ease management burden
- **Less oversight**: no monitoring of employee telecommunications usage
- **Cost savings**: employees responsible for own device purchases/wireless plans
- **Simplified IT infrastructure**: use existing cellular network
- **Reduced internal service**: users contact wireless carrier for support
- **Increased employee performance**: comfort with device while traveling/working remotely

### Mobile Device Risks

#### Mobile Device Vulnerabilities

| Vulnerability | Description |
|--------------|-------------|
| **Physical security** | Portability is greatest asset and greatest vulnerability; devices routinely lost/stolen (laptop stolen every 53 seconds; 70 million smartphones lost annually) |
| **Limited updates** | Apple commits to 4+ years of OTA updates; Android varies (Google devices: 3 years; other OEMs: 2 years minimum) |
| **Location tracking** | GPS supports geolocation; advantages (navigation, social media, fraud reduction) but risk of targeted physical attacks |
| **GPS tagging (geo-tagging)** | Adding geographical identification data to media; can inadvertently reveal private locations |
| **Unauthorized recording** | Webcams and microphones targeted by attackers to spy on victims |

#### Connection Vulnerabilities

| Vulnerability | Description | Risk |
|--------------|-------------|------|
| **Tethering** | Mobile device shares Internet connection with other devices via Bluetooth/Wi-Fi | Unsecured device may infect tethered devices or corporate network |
| **USB On-the-Go (OTG)** | Device functions as host or peripheral via USB | Malicious flash drive could infect device |
| **Malicious USB cable** | Cable embedded with Wi-Fi controller receiving commands from nearby device | Device recognizes cable as human interface device |
| **Public Wi-Fi** | Free Internet access in restaurants, airports | Attackers eavesdrop on data transmissions |

#### Accessing Untrusted Content

| Source | Description |
|--------|-------------|
| **Unapproved apps** | Users circumvent limitations (jailbreaking on iOS, rooting on Android) to download from unofficial stores (sideloading) |
| **Messaging** | SMS (text only), MMS (pictures/video/audio), RCS (live chat platform); threat actors send links or crafted content |
| **QR codes** | Matrix/two-dimensional barcode storing URLs, text, phone numbers; attackers create malicious QR codes directing to imposter websites |

---

## Objective 2 - Securing Mobile Devices

### Device Configuration

#### Strong Authentication

| Method | Description | Security Level |
|--------|-------------|---------------|
| **Password** | Letters, numbers, characters; most secure but cumbersome on small keyboards | Highest |
| **PIN** | Numbers only (4–16 digits); short PINs predictable (1234 used in 10.71% of PINs) | Moderate |
| **Biometrics** | Fingerprint or facial recognition | High |
| **Swipe pattern** | Draw specific pattern connecting dots; can be detected by shoulder surfing | Lower |

- Screen lock: configurable inactivity timeout (5 seconds to 50 minutes)
- **Smart Lock** (Android): keeps device unlocked in secure settings (pocket/bag, trusted device, specific place)

#### Containerization
- **Segmentation**: separating business apps and data from personal apps and data using "containers"
- Helps avoid data ownership privacy issues
- Allows companies to delete only business data without touching personal data

#### Enable Loss or Theft Services

| Feature | Description |
|---------|-------------|
| **Alarm** | Device generates alarm even if on mute |
| **Last known location** | Shows location on online map when battery low |
| **Locate** | Pinpoint current location on map via GPS |
| **Remote lockout** | Remotely lock device and send custom message to login screen |
| **Thief picture** | Camera takes picture after 3 incorrect passcodes and emails to owner |
| **Remote wipe** | Erase all sensitive data from device |

### Mobile Management Tools

| Tool | Description |
|------|-------------|
| **MDM (Mobile Device Management)** | Server + client components; remote management; OTA updates; configure email/Wi-Fi; detect jailbroken/rooted devices; enforce encryption; enforce geofencing |
| **MAM (Mobile Application Management)** | Application management; distributing and controlling access to apps |
| **MCM (Mobile Content Management)** | Content management for mobile devices; version control, indexing, searching |
| **UEM (Unified Endpoint Management)** | Single management interface for mobile and computer devices; supports MDM, MAM, MCM capabilities |

- **Geofencing**: using device GPS to define geographical boundaries where app can be used

---

## Objective 3 - Embedded Systems and Specialized Devices

### Types of Embedded Devices

#### Hardware and Software Components

| Component | Description |
|-----------|-------------|
| **Raspberry Pi** | Low-cost, credit-card-sized computer motherboard; can browse Internet, play video, create spreadsheets |
| **Arduino** | Controller for other devices; 8-bit microcontroller (vs. 64-bit on Raspberry Pi); limited RAM; no OS; programs written in C11 |
| **FPGA (Field-Programmable Gate Array)** | Hardware chip programmable by user; internal blocks with user-programmable interconnects |
| **SoC (System on a Chip)** | Combines all electronic circuits on single IC chip; often uses RTOS |
| **RTOS (Real-Time Operating System)** | Specifically designed OS for embedded/specialized systems; tuned for high volumes of data requiring immediate processing (high availability) |

- **Hardening RTOS**: improving functionality and security (simplified structures, reliability-enhancing technologies, radiation hardening for space applications)

#### Industrial Systems
- **ICS (Industrial Control Systems)**: collect, monitor, process real-time data for machines to control devices (valves, pumps, motors)
- **SCADA (Supervisory Control and Data Acquisition)**: manages multiple ICSs at remote locations

#### Specialized Systems
- **Smart meters**: replacing analog meters; transmit readings daily/hourly/minutely; tamper protection; "last gasp" notifications
- **Medical systems, aircraft, vehicles**: embedded systems controlling complex functions
- Modern cars: dozens of embedded systems controlling brakes, steering, entertainment, navigation

#### Internet of Things (IoT)
- **IoT**: connecting any device to the Internet for sending/receiving data
- Average household: 22 connected devices (2022); estimated 27 billion IoT devices by 2025
- Examples: thermostats, coffee makers, tire sensors, keyless entry systems, washing machines

### Security Constraints

| Constraint | Explanation |
|-----------|-------------|
| **Power** | Devices optimized for low power; lack ability to perform strong security measures |
| **Compute** | Small devices possess low processing capabilities |
| **Inability to patch** | Few devices designed with capacity for updates |
| **Patch availability** | Many manufacturers do not produce patches |
| **Cost** | Developers focus on making products inexpensive; leave out security |
| **Ease of recovery** | Compromised sensor may have difficulty recovering |
| **Responsiveness** | Security features may impact responsiveness |
| **Scalability** | Increasing size/scope introduces new vulnerabilities |
| **Ease of deployment** | Faster rollout than security can keep up |
| **Risk transference** | Shifting risk between areas creates security holes |
| **Availability** | Overburdening with security hampers access |

- **Resource versus security constraint**: tug-of-war between available resources (time, energy) and security provided by cryptography

### Hardening ICS and SCADA Systems
- Define security roles, responsibilities, and authorities
- Identify security requirements
- Conduct physical security surveys; assess remote sites
- Disconnect unnecessary connections
- Do not rely on proprietary protocols
- Document network architecture
- Establish clear policies and conduct training
- Test to identify and evaluate attack scenarios
- Evaluate and strengthen all connections
- Remove or disable unnecessary services
- Identify all connections to SCADA networks
- Implement IDS and incident monitoring
- Implement vendor-provided security features
- Perform technical audits

### Legislation and Regulations

| Level | Legislation | Description |
|-------|------------|-------------|
| **Federal** | IoT Cybersecurity Improvement Act of 2020 | Requires agencies to increase cybersecurity for federal IoT devices |
| **EU** | Cyber Resilience Act (CRA) 2022 | Sets common security standards for connected devices |
| **State** | California and Oregon IoT laws (2020) | Require "reasonable security features" for connected devices |
| **FDA** | New powers (2022) | Minimum security standards for medical-device manufacturers; software bill of materials; ability to accept patches |

---

## Objective 4 - Application Security

### Attacks Based on Application Vulnerabilities

| Attack | Description | Defense |
|--------|-------------|---------|
| **Executable files attack** | Trick vulnerable app into modifying/creating executable files | Prevent app from creating/modifying executables |
| **System tampering** | Modify special sensitive areas of OS (registry keys, startup files) | Do not allow apps to modify special OS areas |
| **Process spawning control** | Trick vulnerable app into spawning executable files | Remove process spawning ability from app |

### Application Development Concepts

#### General Concepts
- **Development**: establish requirements, confirm business needs before coding
- **Testing**: thoroughly test for errors that could result in security vulnerabilities
- **Staging**: verify code functions as intended
- **Production**: release application to actual setting

#### Development Lifecycle Models

| Model | Description |
|-------|-------------|
| **Waterfall** | Sequential design; each stage fully completed before moving to next; QA occurs only after testing; demands extensive planning |
| **Agile** | Incremental approach; small modules worked in short "sprints" (weekly/monthly); priorities re-evaluated; feedback incorporated before next sprint |

#### SecDevOps
- **SecDevOps** (also DevSecOps, DevOpsSec): integrating secure development best practices into application development using agile model
- Cornerstone: **automation**
- Enables: continuous monitoring, continuous validation, continuous integration, continuous delivery, continuous deployment
- Concepts: **immutable systems** (values not modified; new system created for changes), **infrastructure as code** (managing infrastructure using code principles), **baselining** (creating starting point for comparison)

### Secure Coding Techniques

| Technique | Description | Security Advantage |
|-----------|-------------|-------------------|
| **Input validation** | Account for errors such as incorrect user input | Prevents XSS and CSRF attacks |
| **Normalization** | Organize data to minimize redundancy | Reduces footprint of data exposed |
| **Stored procedure** | Subroutine available to database-accessing applications | Eliminates need to write vulnerable subroutines |
| **Code signing** | Digitally signing applications | Confirms author; guarantees code not altered |
| **Obfuscation/camouflaged code** | Write application so inner functionality is difficult to understand | Prevents attacker understanding program function |
| **Dead code** | Section that executes but performs no meaningful function | Provides unnecessary attack vector |
| **Server/client-side execution and validation** | Input validation on server or client browser | Adds another validation layer |
| **Code reuse of third-party libraries/SDKs** | Use existing vetted software | Eliminates need to write new code |

### Code Testing

| Analysis Type | Description |
|--------------|-------------|
| **Static code analysis** | Analysis/testing from security perspective before source code is compiled; may include manual peer reviews |
| **Dynamic code analysis (runtime verification)** | Testing after source code is compiled; monitors application behavior for memory corruption, privilege issues, security problems |

#### Fuzzing
- **Fuzzing**: provides random input to program to trigger exceptions (memory corruption, crashes, security breaches)
- Produces record of what input triggered exception for reproduction
- Fuzzing test software: execution engine + input generator
- Single pass unlikely to find all exceptions due to randomness; requires multiple trials and statistical tests

---

## Key Terms

- **Agile model** — incremental application development approach with short sprints
- **Arduino** — controller for other devices with 8-bit microcontroller
- **BYOD (Bring Your Own Device)** — users use own personal devices for business
- **Cellular network** — coverage area divided into hexagonal cells with transmitters
- **Containerization** — separating business and personal data into managed containers
- **COPE (Corporate Owned, Personally Enabled)** — employees choose from company-approved devices
- **CYOD (Choose Your Own Device)** — employees choose from limited approved devices
- **Dynamic code analysis** — testing after source code compilation
- **Embedded system** — computer hardware/software for specific function within larger system
- **FPGA (Field-Programmable Gate Array)** — user-programmable hardware chip
- **Fuzzing** — random input testing to trigger exceptions
- **Geofencing** — using GPS to define geographical boundaries for app use
- **Hardening RTOS** — improving RTOS functionality and security
- **ICS (Industrial Control Systems)** — collect, monitor, process real-time data for machine control
- **Input validation** — accounting for errors in user input
- **IoT (Internet of Things)** — connecting any device to the Internet
- **Jailbreaking** — circumventing built-in limitations on Apple iOS devices
- **MDM (Mobile Device Management)** — remote device management by organization
- **Raspberry Pi** — low-cost, credit-card-sized computer motherboard
- **Rooting** — circumventing built-in limitations on Android devices
- **RTOS (Real-Time Operating System)** — OS designed for embedded/specialized systems
- **SCADA (Supervisory Control and Data Acquisition)** — manages multiple ICSs
- **SecDevOps** — integrating secure practices into agile development
- **Sideloading** — downloading apps from unofficial third-party stores
- **Smart meter** — digital utility meter transmitting readings to utility company
- **SoC (System on a Chip)** — combines all electronic circuits on single IC
- **Static code analysis** — testing before source code compilation
- **Waterfall model** — sequential application development lifecycle

---

## Review Questions

1. Ahmet is explaining security constraints for a new embedded system. Which would he NOT include?
   - a. Authentication
   - b. Cost
   - c. Power
   - d. Ease of use

2. Yusuf needs a credit-card-sized motherboard with a microcontroller for a factory floor controller. Which is the best solution?
   - a. SoC
   - b. Raspberry Pi
   - c. Arduino
   - d. FPGA

3. Musa needs a tool with a single management interface for mobile devices, applications, and content. Which tool is best?
   - a. UEM
   - b. MDM
   - c. MCCM
   - d. MMAM

4. Deniz is told employees may choose from a limited list of approved devices but must pay for the device; company provides monthly stipend. Which deployment model is this?
   - a. BYOD
   - b. DYOD
   - c. CYOD
   - d. Corporate-owned

5. Eren is researching Android firmware OTA updates. Which reason would Eren NOT list as a factor in update frequency?
   - a. OEMs are hesitant to distribute updates because it limits differentiation
   - b. Modified Android makes OEMs reluctant to distribute conflicting updates
   - c. Wireless carriers are reluctant due to bandwidth consumption
   - d. OEMs have no financial incentive to update devices users keep using

6. What is the process of identifying the geographical location of a mobile device?
   - a. Geotracking
   - b. Geolocation
   - c. GeoID
   - d. Geomonitoring

7. Which is NOT an advantage of COPE for an enterprise?
   - a. Simplified IT infrastructure
   - b. Cost savings
   - c. Flexibility in management
   - d. More oversight

8. Ceyhun receives a request for USB OTG support. Which would Ceyhun NOT say is an advantage?
   - a. Device can function as peripheral for external media access
   - b. Device can function as host
   - c. USB OTG is only available for Android devices
   - d. Connecting to infected computer could send malware to device

9. Ozan's supervisor reports a new employee attempted to circumvent built-in limitations on her Android smartphone. What is this called?
   - a. Rooting
   - b. Sideloading
   - c. Jailbreaking
   - d. Ducking

10. What is another name for runtime verification?
    - a. Static code analysis
    - b. Dynamic code analysis
    - c. Fuzzering
    - d. Weighted code analysis

11. What is dead code?
    - a. A block of code that does not run
    - b. Code tagged to be removed from an application
    - c. A branch that calls a subroutine but always returns null
    - d. A section that executes but performs no meaningful function

12. Cahill is writing an application using SecDevOps and wants to prevent XSS and CSRF attacks. What coding technique would he use?
    - a. Obfuscation
    - b. Code signing
    - c. Input validation
    - d. Normalization

13. What does containerization do?
    - a. Splits OS functions only on specific brands of mobile devices
    - b. Places all keys in a special vault
    - c. Slows down a mobile device to half speed
    - d. Separates personal data from corporate data

14. What allows a device to be managed remotely?
    - a. MDM
    - b. MAM
    - c. MRM
    - d. MWM

15. Which is NOT a security feature for locating a lost or stolen mobile device?
    - a. Remote lockout
    - b. Last known good configuration
    - c. Alarm
    - d. Thief picture

16. What enforces the location in which an app can function by tracking the location of the mobile device?
    - a. Location resource management
    - b. Geofencing
    - c. GPS tagging
    - d. Graphical management tracking (GMT)

17. Which is considered the strongest type of passcode on a mobile device?
    - a. Password
    - b. PIN
    - c. Fingerprint swipe
    - d. Draw connecting-dots pattern

18. Which is NOT a means by which untrusted content can be sent to a mobile device?
    - a. SMS
    - b. MMS
    - c. RCS
    - d. XRX

19. Which tool manages the distribution and control of apps?
    - a. MAM
    - b. MDM
    - c. MCM
    - d. UEM

20. What is a software bill of materials?
    - a. A list of components included in software
    - b. A manual for software installation
    - c. A list of all software on a device
    - d. A security assessment of software
