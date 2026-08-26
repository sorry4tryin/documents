---
created: 2026-08-25 20:12:00
class:
  - document
description: CompTIA Security+ SY0-701 Module 10 — wireless network attacks, WLAN vulnerabilities, and wireless security solutions
mod.: 2026-08-25 20:12:00
aliases:
  - security+ module 10
  - wireless network attacks
tags:
  - study/security-plus
  - study/security-plus/module-10
---

# Module 10 - Wireless Network Attacks and Defenses

## Objectives

1. [[#Objective 1 - Wireless Network Attacks|Describe the different types of wireless network attacks]]
2. [[#Objective 2 - Vulnerabilities of WLAN Security|List the vulnerabilities of WLAN security]]
3. [[#Objective 3 - Wireless Security Solutions|Explain the solutions for securing a wireless network]]

---

## Objective 1 - Wireless Network Attacks

### Cellular Networks
- **Cellular networks**: the most widespread wireless networks, operated by telecommunication service providers
  - End users are **not** responsible for configuring or securing these networks
  - Providers own, maintain, and manage their own network equipment and facilities
- **5G** introduced in 2018 enables fixed wireless service for Internet connectivity
  - Fixed wireless competes against wired cable and fiber optic solutions
  - Advantage: provides Internet access to remote or rural areas lacking wired infrastructure

### Bluetooth Attacks
- **Bluetooth**: wireless technology using short-range **radio frequency (RF)** transmissions, providing rapid device pairings
  - Named after 10th-century Danish King Harald "Bluetooth" Gormsson
  - Originally designed in 1994 by Ericsson to replace personal computer cables
  - Current version: Bluetooth 5.4 (early 2023); all versions backward compatible
- **Personal area network (PAN)** technology for data communication over short distances
- Two implementations:
  - **Bluetooth BR/EDR** (Basic Rate/Enhanced Data Rate, "Bluetooth Classic"): short-range continuous connectivity (e.g., streaming music); 1–3 Mbps
  - **Bluetooth Low Energy (LE)**: short bursts of data over longer distances (e.g., inventory control); 125 Kbps–2 Mbps
- Three device classes by range:
  - Class 1: up to 328 feet (100 m)
  - Class 2: up to 98 feet (30 m)
  - Class 3: up to 33 feet (10 m)
- **Piconet**: primary Bluetooth network topology
  - One device is the **broadcaster** (controls all wireless traffic)
  - Other devices are **observers** (take commands from broadcaster)
  - **Active followers**: connected and sending transmissions
  - **Parked followers**: connected but not actively participating
- Bluetooth LE supports **mesh** topology (many-to-many) to extend range
- **Scatternet**: group of overlapping piconets with connections between them (rarely used)

#### Bluejacking
- Attack that sends **unsolicited messages** to Bluetooth-enabled devices (text, images, sounds)
- Usually more annoying than harmful; no data is stolen
- Has been used for advertising by vendors

#### Bluesnarfing
- Attack that accesses **unauthorized information** from a wireless device through a Bluetooth connection
- Attacker copies emails, calendars, contact lists, pictures, or videos without knowledge or permission
- Mitigation: turn off Bluetooth when not needed, make device non-discoverable, or reject pairing requests from unknown devices

### Near Field Communication (NFC) Attacks
- **Near field communication (NFC)**: set of standards for communication between devices in very close proximity (within 4 cm)
- **Passive NFC device** (e.g., NFC tag): contains information that other devices can read; transmits only
- **Active NFC device**: can both read and transmit data
- NFC communication process:
  1. Smartphone (interrogator) sends signal; tag becomes powered by the interrogator's wireless signal
  2. Both create high-frequency magnetic fields → **magnetic induction** forms connection
  3. Interrogator sends message to determine tag's communication type
  4. Tag validates instructions; for sensitive transactions, a secure encrypted channel is established
- Uses: entertainment (tickets, smart posters), office (access control, time clocks), retail (coupons, reward cards), transportation (turnstiles, schedules)
- **Contactless payment system**: NFC payment method using a "virtual wallet" on a watch or smartphone at an NFC-enabled PoS terminal

#### NFC Risks and Defenses

| Vulnerability | Explanation | Defense |
|---|---|---|
| **Eavesdropping** | Unencrypted NFC communication can be intercepted | Remain aware of surroundings; attacker must be extremely close |
| **Data theft** | Attacker "bumps" a portable reader to a user's smartphone in a crowd | Turn off NFC in large crowds |
| **Man-in-the-middle** | Attacker intercepts NFC communications and forges fictitious responses | Configure pairing so one device sends while the other receives |
| **Device theft** | Stolen smartphone used for purchases | Protect smartphones with passwords or strong PINs |

### Radio Frequency Identification (RFID) Attacks
- **Radio frequency identification (RFID)**: transmits information between paper-based tags and proximity readers
- **Passive RFID tags**: no own power supply; powered by incoming signal from transceiver
  - Very small (0.4 mm × 0.4 mm), thinner than a sheet of paper
  - Limited to just an ID number; range from 1/3 inch to 19 feet
- **Active RFID tags**: require own power source
- Operates in three bands: low frequency (LF), high frequency (HF), ultra-high frequency (UHF)

#### RFID Attack Types

| Attack Type | Description | Implication |
|---|---|---|
| **Unauthorized tag access** | Rogue RFID reader determines store inventory | Rival manufacturer uses sales data for negotiation |
| **Fake tags** | Authentic tags replaced with fake ones containing fictitious data | Undermines inventory system integrity |
| **Eavesdropping** | Unauthorized users listen to tag-reader communications | Confidential data exposed (e.g., purchase records) |
| **RFID cloning** | Capturing data and using it nefariously | Transfers price from cheap to expensive item (e.g., $10 t-shirt to $1,000 coat) |

- RFID also embedded in: Enhanced Driver's Licenses (EDLs), passports, hotel key cards
- Risk of eavesdropping is not considered high due to short LF range (4 inches) and passport must be open to transmit

### Wireless Local Area Network (WLAN) Attacks
- **Wireless local area network (WLAN)**: commonly called Wi-Fi; designed to replace or supplement a wired LAN
- IEEE developed WLAN standards; Wi-Fi Alliance adopted consumer-friendly version numbers in 2018

#### WLAN Versions

| IEEE Name | Wi-Fi Version | Date | Frequency (GHz) | Max Data Rate |
|---|---|---|---|---|
| 802.11 | None | 1997 | 2.4 | 2 Mbps |
| 802.11b | Wi-Fi 1 | 1999 | 2.4 | 11 Mbps |
| 802.11a | Wi-Fi 2 | 1999 | 5 | 54 Mbps |
| 802.11g | Wi-Fi 3 | 2003 | 2.4 | 54 Mbps |
| 802.11n | Wi-Fi 4 | 2009 | 2.4 and 5 | 600 Mbps |
| 802.11ac | Wi-Fi 5 | 2014 | 5 | 7.2 Gbps |
| 802.11ax | Wi-Fi 6 | 2019 | 2.4 and 5 | 9.6 Gbps |
| 802.11ax | Wi-Fi 6E | 2020 | 2.4, 5, and 6 | 9.6 Gbps |

- Three driving forces for new versions: new wireless technologies, new spectrum, increased security

#### WLAN Hardware
- **Wireless client network interface card (wireless adapter)**: embedded antenna to send/receive signals
- **Wireless access point (AP)**: centrally located connection device (antenna, radio transmitter/receiver, bridging software, wired interface)
  - **Infrastructure mode**: WLAN using an AP
  - **Ad hoc mode** (IBSS): devices communicate without an AP
- **Wireless router**: combines AP, firewall, router, and DHCP server (residential WLAN gateway)
- Enterprise AP types:
  - **Fat AP** (autonomous AP): self-contained intelligence for wireless management; good for small offices
  - **Thin AP** (lightweight AP): configuration centralized in wireless switch; better for large deployments
  - **Controller AP**: managed through dedicated **wireless LAN controller (WLC)**; settings auto-distributed
    - Advantages: faster handoffs, monitoring tools, centralized configuration
    - Disadvantages: proprietary (must be same vendor), doesn't fully integrate wired/wireless
  - **Captive portal AP**: uses standard web browser to present AUP or login credentials before access

#### WLAN Enterprise Attacks
- Traditional wired networks have a **hard edge** (single entry point + security appliances + building walls)
- WLANs create **blurred edges**: multiple RF entry points, signals extend beyond building perimeter
- **Rogue AP**: unauthorized AP that allows attackers to bypass network security configurations
  - Can be software-based (e.g., Windows SoftAP, virtual Wi-Fi)
  - Attacker behind firewall can inject malware, steal data
- **Evil twin**: attacker's AP designed to mimic an authorized AP; users unknowingly connect and have transmissions captured
- **Intercepting wireless data**: attacker picks up RF signal from open/misconfigured AP; can also read wired network traffic via rogue AP

#### Wireless Denial Attacks
- **Jamming**: attacker floods RF spectrum with extraneous signal noise to prevent communications
  - Rare; requires expensive equipment and close range (location can be identified)
- **Disassociation attack**: exploits IEEE 802.11 implicit trust of management frames
  - Attacker sends false deauthentication/disassociation frames to disconnect client from AP
  - Client can reconnect, but attacker continues sending spoofed frames
  - IEEE 802.11w amendment partially addresses but not widely implemented
- **Duration field values attack**: exploits RTS/CTS protocol
  - Attacker sends frame with duration field set to arbitrarily high value (max 32,767)
  - All stations store this in **net allocation vector (NAV)** field; no station can transmit while NAV ≠ 0

#### WLAN Consumer Attacks
- On unsecured or improperly configured wireless routers, attackers can:
  - **Steal data**: access folders with file sharing enabled
  - **Read wireless transmissions**: capture usernames, passwords, credit card numbers
  - **Inject malware**: access network behind firewall
  - **Download harmful content**: plant illegal content on computer, distribute via file server

---

## Objective 2 - Vulnerabilities of WLAN Security

### Wired Equivalent Privacy (WEP)
- **WEP**: IEEE 802.11 security protocol ensuring only authorized parties can view transmitted information via encryption
- Uses a **shared secret key** (minimum 64 bits; vendors offer 128 bits) combined with an **initialization vector (IV)** (24-bit value changing per packet)
- IV and key combined as seed for encryption; both IV and ciphertext transmitted to receiver

#### WEP Vulnerabilities
1. Short IV length (24 bits) limits strength; shorter keys easier to break
2. Creates **detectable patterns**: only 16,777,216 possible IV values; busy AP (700 packets/sec at 11 Mbps) produces IV duplicates in fewer than 7 hours
3. Attacker captures packets, identifies duplicates, and cracks encryption
4. Windows 11 and updated Windows 10 no longer support WEP

### Wi-Fi Protected Setup (WPS)
- **WPS**: optional means of configuring WLAN security for users with little security knowledge
- Two methods:
  - **PIN method** (mandatory): PIN printed on router sticker or displayed through software wizard
  - **Push-button method** (mandatory for routers, optional for devices): user pushes button on router and device

#### WPS PIN Vulnerabilities
- No lockout limit for PIN entry attempts (unlimited tries)
- Last PIN character is only a checksum
- Router reports validity of first and second PIN halves separately
- Only 11,000 different PINs to try (not 100 million)
- Attacker can crack PIN in less than 4 hours at 1.3 attempts/second
- Recommendation: disable WPS through configuration settings

### MAC Address Filtering
- **MAC address filtering**: controls which devices can connect to the WLAN based on their unique 48-bit hardware address
  - Typically implemented by **permitting** (allow list) rather than preventing (block list)

#### MAC Filtering Vulnerabilities
- MAC addresses are exchanged in **unencrypted** format between devices and AP
- Attacker can monitor airwaves, see approved MAC address, and spoof it
- Managing several MAC addresses is challenging in large, dynamic networks

### Hiding SSID
- **Service Set Identifier (SSID)**: user-supplied network name (up to 32 alphanumeric characters)
- SSID normally broadcast; can be restricted so only users who know it in advance can connect
- **Not recommended**: SSID easily discovered through other management frames even when not in beacon frames

### Wi-Fi Protected Access (WPA)
- **WPA**: introduced to fit into existing WEP engine without extensive hardware upgrades
- Two modes: WPA-Personal (SOHO, ≤10 employees) and WPA-Enterprise (larger organizations)
- **Preshared key (PSK)**: secret value manually entered on AP and each wireless device
  - Devices with the key are automatically authenticated
- WPA improves over WEP but has weaknesses; **not considered secure**

---

## Objective 3 - Wireless Security Solutions

### Wi-Fi Protected Access 2 (WPA2)
- Based on IEEE 802.11i standard; two modes: WPA2-Personal and WPA2-Enterprise
- Addresses encryption and authentication

#### AES-CCMP Encryption
- **Counter Mode with Cipher Block Chaining Message Authentication Code Protocol (CCMP)**: cryptographic wireless protocol for WPA2
- Uses **CCM** (cipher mode for data privacy) with **AES**
- **Cipher Block Chaining Message Authentication Code (CBC-MAC)**: component providing data integrity and authentication
- CCMP for WLANs sometimes designated as **AES-CCMP**

#### IEEE 802.1x Authentication
- **IEEE 802.1x**: port-based authentication standard for WPA2-Enterprise
- Blocks all traffic until client is authenticated using credentials on an authentication server
- Process:
  1. **Supplicant** (device) requests permission from **authenticator** to join network
  2. Authenticator asks supplicant to verify identity
  3. Supplicant sends identity to authenticator
  4. Authenticator passes identity to **authentication server** (encrypted)
  5. Authentication server verifies or rejects identity
  6. If approved, supplicant joins network and transmits data
- Also usable for wired networks (e.g., conference room: trusted employees access corporate network + Internet; public users restricted to Internet only)

#### Extensible Authentication Protocol (EAP)
- **EAP**: framework for transporting authentication protocols (not the authentication protocol itself)
- Defines message format; uses four packet types: request, response, success, failure
- **Protected EAP (PEAP)**: simplifies 802.1x deployment using Microsoft Windows logins/passwords
  - Creates encrypted channel between client and authentication server
  - Client first authenticates server using enhanced authentication

#### Common EAP Protocols

| EAP Name | Description |
|---|---|
| **EAP-TLS** | Uses digital certificates for authentication |
| **EAP-TTLS** | Securely tunnels client password authentication within TLS records |
| **EAP-FAST** | Securely tunnels any credential form (password, token) using TLS |

### Wi-Fi Protected Access 3 (WPA3)
- Next generation of WPA; hardware certification program specifying required standards
- Two modes: WPA3-Enterprise and WPA3-Personal; optional **WPA3-Enterprise 192-bit mode** (highest security)

#### WPA3 Security Improvements
- **Simultaneous Authentication of Equals (SAE)**: increases security during handshake when keys are exchanged; stronger security even with short/weak passwords
- **Protected Management Frames (PMFs)**: mitigate against disassociation attacks
- Improved interaction with IoT devices (many have no screens for configuration)
- **Opportunistic Wireless Encryption (OWE)**: on open/public Wi-Fi, applies individualized data encryption (unique key per client-AP connection); mitigates MITM attacks (optional)
- **Wi-Fi Easy Connect**: supersedes WPS; uses QR code or NFC tag to connect devices (optional)

### Additional Wireless Security Protections

#### Installation — Site Survey
- **Site survey**: in-depth examination and analysis of a WLAN site to place APs in optimum location
- Ensures: adequate wireless coverage, reasonable bandwidth, minimum signal bleed outside building

#### Site Survey Tools
- **Heat map**: visual representation of wireless signal coverage overlaid on floorplan
- **Wi-Fi analyzer**: visualizes signal strength, network health, channel bandwidth, data rate, interference
- **Channel overlays**: software illustrating conflicting channel overlaps between multiple APs

#### Configuration
- **Signal strength settings**: adjust transmit power (1–200 mW) to limit signal reaching outside premises
- **Spectrum selection**:
  - Disable unused frequency bands
  - Use Auto mode for channel selection or choose non-overlapping channels
  - Larger channel widths more subject to interference

#### Antenna Placement and Type
- APs should be mounted as high as possible (fewer obstructions, theft prevention)
- Position antenna to focus signal toward authorized users instead of wide-area broadcast

#### Rogue AP System Detection
- **Rogue AP system detection**: identifying unauthorized devices in an enterprise
- Requires **wireless probe**: device that monitors airwaves for traffic
- Four types of wireless probes:
  1. **Wireless device probe**: standard laptop configured to scan/record signals when idle; multiple probes provide high accuracy
  2. **Desktop probe**: desktop PC with USB wireless adapter monitoring RF
  3. **Access point probe**: AP with additional neighbor detection functionality (limited range)
  4. **Dedicated probe**: designed exclusively to monitor RF for transmissions
- Detected suspicious signals sent to **WLAN management system**; compared against approved APs
- Unauthorized devices flagged as rogue; switch port can be disabled to sever connection

---

## Key Terms

- **bluejacking** — attack sending unsolicited messages to Bluetooth devices
- **bluesnarfing** — attack accessing unauthorized information via Bluetooth
- **Bluetooth** — short-range RF wireless technology using piconets
- **Cipher Block Chaining Message Authentication Code (CBC-MAC)** — component of CCMP providing data integrity and authentication
- **Counter Mode with Cipher Block Chaining Message Authentication Code Protocol (CCMP)** — cryptographic protocol for WPA2 encryption using AES
- **disassociation attack** — attack exploiting unverified management frames to disconnect clients
- **duration field values attack** — attack exploiting RTS/CTS to prevent device transmission
- **EAP-FAST** — EAP protocol tunneling any credential form using TLS
- **EAP-TLS** — EAP protocol using digital certificates for authentication
- **EAP-TTLS** — EAP protocol tunneling password authentication within TLS records
- **evil twin** — attacker's AP mimicking an authorized AP
- **Extensible Authentication Protocol (EAP)** — framework for transporting authentication protocols
- **heat map** — visual representation of wireless signal coverage
- **jamming** — flooding RF spectrum with noise to prevent communications
- **Protected EAP (PEAP)** — EAP protocol simplifying 802.1x using Windows logins
- **radio frequency identification (RFID)** — technology transmitting information between tags and readers
- **RFID cloning** — capturing RFID data and using it nefariously
- **rogue AP** — unauthorized AP that bypasses network security
- **site survey** — in-depth examination of WLAN site for optimal AP placement
- **wireless local area network (WLAN)** — Wi-Fi network replacing/supplementing wired LAN

---

## Review Questions

1. Simiso has been asked to research a new payment system for the retail stores that her company owns. Which technology is predominantly used for contactless payment systems that she will investigate?
   a. Bluetooth
   b. Near field communication (NFC) ✓
   c. Wi-Fi
   d. Radio Frequency ID (RFID)

2. Muchaneta is investigating a security incident in which the smartphone of the CEO was compromised and confidential data was stolen. She suspects that it was an attack that used Bluetooth. Which attack would this be?
   a. Blueswiping
   b. Bluehiking
   c. Bluejacking
   d. Bluesnarfing ✓

3. What is a difference between NFC and RFID?
   a. NFC is based on wireless technology while RFID is not.
   b. RFID is faster than NFC.
   c. NFC requires the sender to be very close to the receiver. ✓
   d. NFC devices cannot pair as quickly as RFID devices.

4. Which of the following attacks transfers the data from one RFID tag to another?
   a. RFID swiping
   b. RFID cloning ✓
   c. RFID duplicating
   d. RFID mirroring

5. Thubelihle has just been informed that an employee has tried to install their own wireless router in the employee lounge. Why is installing this rogue AP an issue?
   a. It uses the weaker IEEE 80211i protocol.
   b. It allows an attacker to bypass network security configurations. ✓
   c. It conflicts with other network firewalls and can cause them to become disabled.
   d. It requires the use of vulnerable wireless probes on all mobile devices.

6. Zendaya is helping her neighbor install and configure a new wireless router. Her neighbor is reluctant to configure the settings on the device but just wants to accept the default settings. Which of these is NOT a reason Zendaya would give regarding the risks of an improperly configured wireless router?
   a. An attacker can steal data from any folder with file sharing enabled.
   b. Wireless devices could be susceptible to an INKSPOT attack. ✓
   c. User names, passwords, credit card numbers, and other information sent over the WLAN could be captured by an attacker.
   d. Malware can be injected into a computer connected to the WLAN.

7. Which of these WPS methods is vulnerable?
   a. Push-button
   b. PIN ✓
   c. NXC
   d. Click-to-send

8. Zuri is on vacation and visits a local coffee shop to enjoy a beverage and check her email through the free Wi-Fi. When she first connects, a screen appears asking her to agree to an acceptable use policy (AUP) before continuing. What type of AP portal has she encountered?
   a. Rogue portal
   b. Approval portal
   c. Limited portal
   d. Captive portal ✓

9. Which of the following is NOT a wireless denial attack that attempts to prevent a user from accessing or using a WLAN?
   a. RTS/CTS replay attack ✓
   b. Duration field values attack
   c. Disassociation attack
   d. Jamming

10. Nia is writing an email to an employee about a wireless attack that is designed to capture wireless transmissions from legitimate users. Which type of attack is she describing?
    a. NFC capture attack
    b. Evil twin attack ✓
    c. WPA grab attack
    d. Sleeper attack

11. Which of these is a vulnerability of MAC address filtering in a WLAN?
    a. Not all operating systems support MACs.
    b. APs use IP addresses instead of MACs.
    c. The user must enter the MAC.
    d. MAC addresses are initially exchanged unencrypted. ✓

12. Which of the following is NOT true about cellular networks?
    a. Using a cellular network requires extensive security configurations on the part of the user. ✓
    b. Cellular networks are operated by telecommunication service providers.
    c. The telecommunication service providers of cellular networks own, maintain, and manage their own network equipment and facilities.
    d. The most widespread wireless networks are cellular networks.

13. Which of the following is NOT true about WLAN versions?
    a. New versions of WLANs have appeared regularly.
    b. Updated versions have resulted in increased speed, coverage area, and resistance to interference and stronger security.
    c. WLAN standards are set by the IEEE.
    d. WLAN-IEEE 8ax is the final version to be released. ✓

14. Which of these is the encryption protocol for WPA2?
    a. IEEE 802.1x
    b. CCMP ✓
    c. XAP
    d. CBC-MAC

15. Which mode provides the highest level of security?
    a. WEP mode
    b. WPA2-Enterprise mode
    c. WPA4-X mode
    d. WPA3-Enterprise 192-bit mode ✓

16. Nala needs to purchase WLCs for the office. What type of AP must she also purchase that can be managed by a WLC?
    a. Stand-alone AP
    b. Controller AP ✓
    c. Fat AP
    d. Any type of AP can be managed by a WLC.

17. Which WPA3 security feature is designed to increase security at the time of the handshake?
    a. WEP
    b. SAE ✓
    c. OWE
    d. PXF

18. Hadiza is explaining the EAP to a new hire. What would be the best explanation of EAP?
    a. It is the transport protocol used in TCP/IP for authentication.
    b. It is a framework for transporting authentication protocols. ✓
    c. It is a subset of WPA2.
    d. It is a technology used by IEEE 802.11 for encryption.

19. Makena has been asked to recommend an EAP for a system that uses both passwords and tokens with TLS. Which should she recommend?
    a. EAP-SSL
    b. EAP-TLS
    c. EAP-TTLS
    d. EAP-FAST ✓

20. Which of these is a WPA3 technology that mitigates against association attacks?
    a. OWE
    b. SAE
    c. XR3
    d. PMF ✓
