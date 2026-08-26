---
created: 2026-08-20 14:00:00
class:
  - document
description: CompTIA Security+ SY0-701 Module 7 — authentication credentials, best practices, and access controls
mod.: 2026-08-20 14:00:00
aliases:
  - security+ module 7
  - identity and access management
tags:
  - study/security-plus
  - study/security-plus/module-7
---

# Module 7 - Identity and Access Management (IAM)

## Objectives

1. [[#Objective 1 - Authentication Credentials|Describe different types of authentication credentials]]
2. [[#Objective 2 - Authentication Best Practices|List authentication best practices]]
3. [[#Objective 3 - Access Controls|Define access controls and explain how they can be used]]

---

## Objective 1 - Authentication Credentials

### What Is IAM?
- **IAM (Identity and Access Management)**: technologies providing control over user validation and resources that may be accessed
- Ensures the right users access the right digital resources at the right time for the right reasons
- Requires **unique digital identity** (differentiates user from all others) and **identity proofing (authentication)**: process of ensuring the person or system is authentic and not an imposter

### Seven Elements of Authenticity

| Element | Description | Example |
|---------|-------------|---------|
| **Somewhere you are** | Restricted location | Restricted military base |
| **Something you are** | Unique biological characteristic | Fingerprint reader |
| **Something you have** | Possession of unique item | ID card |
| **Someone you know** | Validated by another person | Known by staff |
| **Something you exhibit** | Genetically determined characteristic | Distinctive appearance |
| **Something you can do** | Perform uncopiable activity | Signature |
| **Something you know** | Knowledge nobody else possesses | Combination/password |

- Three elements (know, have, are) are called **factors**
- Four elements (somewhere, can do, exhibit, know someone) are called **attributes**

---

### Something You Know: Passwords

#### How Passwords Work
- User creates username and password → transmitted to server
- Server converts password to **message digest** using **one-way hash algorithm** (scrambled characters)
- Original unscrambled password is NOT stored (security: stolen list would give immediate access)
- On login: server creates new digest from entered password → compares with stored digest → match = access granted

#### Password Weaknesses
- Based on **human memory**: secure repository but limited capacity
- Effective passwords are long and complex but difficult to memorize and recall
- Users must remember **multiple passwords** (average 130–207 accounts per user)
- Each account should have unique password (further strains memory)
- Passwords may expire periodically (45–60 days) and cannot be recycled
- **Predictable patterns**: appending (letters + numbers), replacing (0 for o, 1 for l, $ for s)
- 4 out of 5 enterprise data breaches caused by weak passwords; half of users use one password for all accounts

#### Ten Most Common Passwords (2023)

| Rank | Password |
|------|----------|
| 1 | 123456 |
| 2 | 123456789 |
| 3 | qwerty |
| 4 | password |
| 5 | 12345 |
| 6 | qwerty123 |
| 7 | 1q2w3e |
| 8 | 12345678 |
| 9 | 111111 |
| 10 | 1234567890 |

#### Password Attacks

##### Low-Outcome Attacks

| Attack | Description |
|--------|-------------|
| **Online brute force** | Every possible combination tried on single account; rarely used due to low success and account lockout after limited incorrect attempts |
| **Password spraying** | One or few common passwords tried across many accounts; less likely to raise alarms |

##### High-Outcome Attacks (Based on Password Digest Files)

| Attack | Description |
|--------|-------------|
| **Offline brute force** | Stolen digest file loaded; every possible combination created and matched; slowest but most thorough |
| **Dictionary attack** | Common dictionary words/phrases used as candidates against stolen digest file |
| **Credential stuffing** | Stolen username/password credentials injected across multiple websites (users reuse passwords) |
| **Rule attack** | Statistical analysis on stolen passwords creates mask of candidate password format (e.g., ?u?l?l?l?l?d?d?d?d) |

##### Common Attack Sequence

| Order | Attack | Purpose |
|-------|--------|---------|
| 1 | Custom wordlist | Download stolen digest |
| 2 | Rule attack | Generate specialized masks |
| 3 | Dictionary attack | Crack common passwords |
| 4 | Dictionary with rules | Refined dictionary attack |
| 5 | Updated wordlist with rules | Create more refined rules |
| 6 | Hybrid attack | Focused dictionary + mask |
| 7 | Mask attack | Attack harder passwords |
| 8 | Brute force | Last resort on remaining |

---

### Something You Have: Tokens and Security Keys

#### Tokens

| Type | Description |
|------|-------------|
| **Hardware token (windowed)** | Small device with window display showing dynamic **OTP (one-time password)** |
| **Software token** | Smartphone app generating OTPs or password supplements |

##### OTP Types

| Type | Description |
|------|-------------|
| **TOTP (Time-based OTP)** | Changes after set period (30–60 seconds); valid only while displayed |
| **HOTP (HMAC-based OTP)** | Event-driven; changes when specific event occurs (e.g., PIN entry) |

##### Software Password Supplements
- **Authentication app**: push notification asking user to approve/deny login attempt
- **SMS text**: authentication code sent via text (NOT considered secure — can be phished/intercepted)
- **MFA fatigue attack**: script generates endless MFA push notifications until user approves to stop them

#### Security Keys
- **Security key**: dongle inserted into USB/Lightning port or held near device (NFC)
- Contains all necessary cryptographic information to authenticate user
- **Attestation**: key pair burned into security key during manufacturing; cryptographically proves user has specific device model
- Many professionals recommend security keys over SMS-based MFA

#### Smart Cards
- Credit-card-sized plastic card holding authentication information
- Generally inserted into card reader connected to computer
- Some are contactless (close proximity to reader)
- **PIV (Personal Identity Verification)**: standard covering all U.S. government employees

---

### Something You Are: Biometrics

#### Physiological Biometrics

| Type | Description | Scanner Type |
|------|-------------|-------------|
| **Retinal scan** | Maps unique patterns of retina using low-energy infrared light | Specialized scanner |
| **Fingerprint** | Ridges and valleys create unique template; static (place finger) or dynamic (swipe finger) | Specialized or standard |
| **Vein recognition** | Palm or finger vein patterns identified through scanning tablet | Specialized |
| **Gait recognition** | Manner of walking uniquely authenticates; >99% accuracy | Floor sensors |
| **Voice recognition** | Unique voice characteristics create template; phonetic cadence makes recording attack difficult | Standard microphone |
| **Iris scan** | Unique random patterns in iris identified | Standard webcam |
| **Facial recognition** | ~80 nodal points measured to create faceprint | Standard webcam |

#### Biometric Disadvantages
- High cost for specialized scanners
- Not foolproof: false negatives (genuine users rejected) and false positives (imposters accepted)
- Can be "tricked" (fingerprints from water glasses)
- **Stolen biometric data cannot be reset** like passwords
- Privacy concerns: who has access to biometric data?

#### Cognitive Biometrics
- Based on perception, thought process, and understanding of user
- Based on life experiences → easier to remember, harder to imitate
- **Windows Picture Password**: select picture, highlight landmarks with gestures (tap, line, circle)
- Other examples: identifying faces, recalling "memorable events" with specific questions

---

### Something You Do: Behavioral Biometrics

#### Keystroke Dynamics
- Recognizes user's unique typing rhythm
- **Dwell time**: time between key press and release
- **Flight time**: time between keystrokes
- User template formed from multiple typing samples
- If both what was entered (password) AND how it was entered (rhythm) are correct → authenticated
- No specialized hardware required; no additional user steps

---

## Objective 2 - Authentication Best Practices

### Securing Passwords

#### Protecting Password Digests

| Technique | Description |
|-----------|-------------|
| **Salting** | Random string added to plaintext password before hashing; makes dictionary/brute force attacks more difficult; ensures same password produces different digests |
| **Peppering** | Message digest encrypted with symmetrical encryption key before storing; does not affect hashing function |
| **Key stretching** | Specialized password hash algorithm intentionally designed to be slower; limits attacker's speed of generating candidates |

##### Key Stretching Algorithms

| Algorithm | Description |
|-----------|-------------|
| **bcrypt** | Configurable number of iterations (rounds) to set "expensive" computation |
| **PBKDF2** | Configurable iterations; similar to bcrypt |
| **Argon2** | Newer; configurable salt (8–16 chars), iterations (default 3), memory usage (default 12) |

- Example: general algorithm = ~95^8 candidates in 5.5 hours; bcrypt = only 71,000 candidates in same time

#### Managing Passwords

| Solution | Description |
|----------|-------------|
| **Enterprise password vaulting** | Protected database on organization's network; provides admin control, password rotation, access levels, session revocation |
| **User password manager** | Software/website storing passwords in single vault protected by master password; drag-and-drop, enhanced encryption |
| **Hardware password keys** | Hardware-based storage; serves as password manager, MFA security key, and file encryption device |

#### Password Best Practices
- Change all **default passwords** before new device placed in service
- **Prohibit password reuse** across accounts
- **Do NOT use password expiration** (Microsoft and NIST recommend against it)
- Set **password age** to at least 1 (prevents immediate reset back to old password)
- **Provisioning**: include password policies (minimum length, age, reuse)
- **De-provisioning**: suspend accounts immediately when employee leaves; delete 30 days later
- **Length > complexity**: longer password always more secure than shorter password

##### Password Length vs Security (95-key keyboard)

| Length | Possible Passwords | Average Attempts to Break |
|--------|-------------------|--------------------------|
| 2 | 9,025 | 4,513 |
| 3 | 857,375 | 428,688 |
| 4 | 81,450,625 | 40,725,313 |
| 5 | 7,737,809,375 | 3,868,904,688 |
| 6 | 735,091,890,625 | 367,545,945,313 |

---

### Secure Authentication Technologies

#### Single Sign-On (SSO)
- **Identity management**: single authentication credential shared across multiple networks
- **Federation (FIM)**: identity management across networks owned by different organizations
- **SSO**: one authentication credential to access multiple accounts/applications

##### SSO Technologies

| Technology | Description |
|-----------|-------------|
| **SAML** | XML standard allowing secure web domains to exchange user authentication/authorization data; credentials stored with single identity provider |
| **LDAP** | Protocol enabling users to access network resource through directory service; open protocol for SSO |
| **OAuth** | Open-source federation framework (OAuth 2.0); supports development of authorization protocols; uses token credentials |
| **OpenID** | Open standard decentralized authentication protocol; can be used in OAuth 2.0 |
| **Shibboleth** | Open-source software for designing SSO; uses federation standards |

#### Passwordless Systems
- **Passkeys**: methods for storing authenticating information in hardware
- Combine multiple factors (smartphone + biometric) into single package managed by device OS
- Completely resistant to credential phishing, credential stuffing, and similar attacks
- "Discoverable": enrolled device can push passkey through encrypted tunnel to another enrolled device
- Microsoft, Apple, Google unified around single passkey standard (late 2022)

---

## Objective 3 - Access Controls

### What Are Access Controls?
- **Access control**: granting or denying approval to use specific resources once authenticated
- Based on time: **just-in-time permissions**, **time-of-day restrictions**, **temporal accounts** (one-time access)
- Must consider: why permissions are given, to whom, and impact (**permission assignments and implications**)

### Access Control Schemes

| Scheme | Description | Restrictiveness |
|--------|-------------|----------------|
| **DAC (Discretionary Access Control)** | Object owner has total control; can grant permissions to others | Least restrictive |
| **MAC (Mandatory Access Control)** | Access strictly according to custodian's desires; labels + levels hierarchy | Most restrictive |
| **RBAC (Role-Based Access Control)** | Permissions assigned to roles; users assigned to roles | "Real-world" approach |
| **Rule-Based Access Control** | Dynamically assigns roles based on set of rules defined by custodian | Used for multi-system access |
| **ABAC (Attribute-Based Access Control)** | Flexible policies combining attributes; If-Then-Else structure | Most flexible |

#### DAC Details
- Used on major OSs (e.g., Windows permissions)
- **Weakness 1**: relies on user decisions; incorrect permissions may be granted
- **Weakness 2**: subject's permissions inherited by executed programs; malware runs at same privilege level

#### MAC Details
- **Labels**: every object assigned classification (confidential, secret, top secret); subjects assigned clearance
- **Levels**: hierarchy where top secret > secret > confidential
- Subject must have equal or greater level than object for access
- **Windows MIC (Mandatory Integrity Control)**: SID linked to integrity levels (low, medium, high, system)

#### RBAC Details
- Permissions assigned to roles (e.g., Business_Manager); users assigned to roles
- Users and objects inherit all permissions for the role
- More scalable than DAC for enterprise environments

#### Rule-Based Access Control Details
- Rules contained in resource objects determine access
- Often used when business changes trigger access changes (e.g., router rules based on network address)
- Cannot be changed by users; all permissions controlled by custodian/administrator

#### ABAC Details
- Uses policies combining object, subject, and environment attributes
- If-Then-Else structure (e.g., "If subject has role of manager, then grant access else deny")
- Can enforce both DAC and MAC schemes

### Access Control Lists (ACLs)
- **ACL**: set of permissions attached to an object specifying who can access and what operations allowed
- Most often viewed in relation to files maintained by OS filesystem
- Also ported to SQL and relational database systems
- **Limitations**: not efficient (checked every time resource accessed); difficult to manage in enterprise settings

---

## Key Terms

- **ABAC (Attribute-Based Access Control)** — flexible policies combining attributes
- **ACL (Access Control List)** — permissions attached to an object
- **Attestation** — key pair burned into security key during manufacturing
- **Biometrics** — authentication based on physical/behavioral characteristics
- **Brute force attack** — trying every possible combination
- **Credential stuffing** — injecting stolen credentials across multiple websites
- **DAC (Discretionary Access Control)** — owner has total control; least restrictive
- **Dictionary attack** — using common words as candidates
- **Federation (FIM)** — identity management across different organizations
- **IAM (Identity and Access Management)** — technologies for user validation and resource access control
- **Identity proofing** — process of ensuring person/system is authentic
- **Key stretching** — specialized hash algorithms designed to be slower
- **LDAP (Lightweight Directory Access Protocol)** — protocol for directory service access
- **MAC (Mandatory Access Control)** — strict custodian-controlled access; most restrictive
- **MFA (Multifactor Authentication)** — combining multiple authentication factors
- **OAuth** — open-source federation framework
- **Password manager** — software storing passwords in protected vault
- **Password spraying** — trying common passwords across many accounts
- **Passkeys** — hardware-stored authentication methods replacing passwords
- **RBAC (Role-Based Access Control)** — permissions assigned to roles
- **Rule-Based Access Control** — dynamic role assignment based on rules
- **SAML** — XML standard for exchanging authentication data
- **Salting** — random string added to password before hashing
- **Security key** — dongle containing cryptographic authentication information
- **Smart card** — credit-card-sized card for authentication
- **SSO (Single Sign-On)** — one credential for multiple accounts
- **TOTP (Time-based OTP)** — changes after set time period
- **HOTP (HMAC-based OTP)** — event-driven one-time password

---

## Review Questions

1. How is SAML used?
   - a. It serves as a backup to a directory server
   - b. It allows secure web domains to exchange user authentication and authorization data
   - c. It is an authenticator in IEEE 802.1x
   - d. It is no longer used because it has been replaced by LDAP

2. Amahle is researching elements that prove authenticity. Which is based on unique biological characteristics?
   - a. Something you exhibit
   - b. Something you have
   - c. Something you are
   - d. Something about you

3. Which is NOT true about passwords?
   - a. The weakness of passwords is based on human memory
   - b. The most effective passwords are short but complex
   - c. For the highest level of security, each account should have a unique password
   - d. The security of passwords is based on human memory

4. Imka needs to recommend a federation system technology that is an open-source framework supporting authorization protocols. Which would she recommend?
   - a. OAuth
   - b. Open ID
   - c. Shibboleth
   - d. NTLM

5. How is key stretching effective in resisting password attacks?
   - a. It takes more time to generate candidate password digests
   - b. It requires the use of GPUs
   - c. It does not require the use of salts
   - d. The license fees are very expensive to purchase for use

6. Which is NOT a key stretching algorithm?
   - a. PBKDF2
   - b. bcrypt
   - c. Argon2
   - d. MD5

7. Kerem is creating a password policy. Which would be considered a best practice?
   - a. Require password expiration every 60 days
   - b. Allow password reuse after 90 days
   - c. Set minimum password length to 15 characters
   - d. Require complex passwords of at least 8 characters

8. Elif is explaining why SMS text authentication is not considered secure. Which reason would Elif NOT give?
   - a. SMS texts can be phished
   - b. SMS texts can be intercepted
   - c. SMS texts are expensive to send
   - d. MFA fatigue attacks can be used

9. Which access control scheme is the most restrictive?
   - a. DAC
   - b. MAC
   - c. RBAC
   - d. ABAC

10. Cem is setting up access controls for a new enterprise system. He wants to assign permissions based on job functions. Which scheme should Cem use?
    - a. DAC
    - b. MAC
    - c. RBAC
    - d. Rule-Based

11. Which of the following is an advantage of a security key over SMS authentication?
    - a. Security keys are less expensive
    - b. Security keys do not transmit OTPs or authentication codes
    - c. Security keys are easier to use
    - d. Security keys work with all devices

12. What is the primary purpose of salting?
    - a. To make passwords longer
    - b. To make dictionary attacks and brute force attacks more difficult
    - c. To encrypt passwords before storage
    - d. To generate one-time passwords

13. Which biometric method uses the unique patterns of blood vessels in the retina?
    - a. Fingerprint scan
    - b. Retinal scan
    - c. Iris scan
    - d. Facial recognition

14. What is the difference between dwell time and flight time in keystroke dynamics?
    - a. Dwell time is between keystrokes; flight time is key press to release
    - b. Dwell time is key press to release; flight time is between keystrokes
    - c. Both measure the same thing
    - d. Neither is used in keystroke dynamics

15. Which SSO technology is an XML standard for exchanging authentication data?
    - a. LDAP
    - b. OAuth
    - c. SAML
    - d. OpenID

16. What is the main disadvantage of using biometrics for authentication?
    - a. Biometrics are too expensive
    - b. Biometrics are not accurate
    - c. Stolen biometric data cannot be reset
    - d. Biometrics require special hardware

17. Which access control scheme dynamically assigns roles based on rules?
    - a. DAC
    - b. MAC
    - c. RBAC
    - d. Rule-Based

18. What is the purpose of peppering?
    - a. To add random characters to passwords
    - b. To encrypt password digests before storing
    - c. To make passwords longer
    - d. To generate salt values

19. Which type of token changes its value after a set period of time?
    - a. HOTP
    - b. TOTP
    - c. Smart card
    - d. Security key

20. What is the most critical factor in a strong password?
    - a. Complexity
    - b. Length
    - c. Uniqueness
    - d. Expiration
