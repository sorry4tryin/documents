---
created: 2026-08-19 20:12:00
class:
  - document
description: CompTIA Security+ SY0-701 Module 4 — digital certificates, PKI, secure protocols, and cryptography implementation
mod.: 2026-08-19 20:12:00
aliases:
  - security+ module 4
  - advanced cryptography
tags:
  - study/security-plus
  - study/security-plus/module-4
---

# Module 4 - Advanced Cryptography

## Objectives

1. [[#Objective 1 - Digital Certificates|Define digital certificates]]
2. [[#Objective 2 - Public Key Infrastructure (PKI)|Describe the components of Public Key Infrastructure (PKI)]]
3. [[#Objective 3 - Secure Communication and Transport Protocols|List the secure communication and transport protocols]]
4. [[#Objective 4 - Implementing Cryptography|Explain how to implement cryptography]]

---

## Objective 1 - Digital Certificates

### Defining Digital Certificates
- **Digital certificate**: technology used to associate a user's identity to a public key, digitally signed by a trusted third party
- A **verified container for a public key** — binds the public key to the certificate owner
- Can authenticate: users, websites, organizations, devices, servers, emails, applications

#### Certificate Contents
- Owner's name or alias
- Owner's public key
- Name of the issuer
- Digital signature of the issuer
- Serial number
- Expiration date
- Optional: email address, postal address, basic registration information

#### The Imposter Key Problem
- Digital signatures alone can only prove the **owner of the private key**, not the true identity
- A malicious actor (Mallory) could create imposter public/private key pairs using someone else's identity
- **Solution**: trusted third party verification — like a passport system where a government agency verifies identity

### Managing Digital Certificates

#### Certificate Authorities and the CSR Process

| Car Title Scenario | Digital Certificate Element | Explanation |
|-------------------|---------------------------|-------------|
| Car title application | **CSR (Certificate Signing Request) generation** | Formal request for digital certificate |
| Sign car title application | Create and affix public key | Added to certificate for security |
| Visit county courthouse | **Intermediate certificate authority** | Party that can process CSR on behalf of CA |
| Title sent from state DMV | **Certificate authority (CA)** | Party responsible for digital certificates |

#### Authentication Methods for Certificate Requests
- **Email**: simplest form; identified only by email address; insufficient for other verifications
- **Documents**: registration authority confirms authenticity via birth certificate, employee badge with photo
- **In person**: applicant proves existence and identity with government-issued passport or driver's license

#### Certificate Management

| Component | Description |
|-----------|-------------|
| **Certificate Repository (CR)** | Publicly accessible centralized directory of digital certificates for viewing status |
| **Certificate Revocation List (CRL)** | List of certificate serial numbers that have been revoked |
| **OCSP (Online Certificate Status Protocol)** | Real-time lookup of certificate status; request-response protocol |
| **OCSP stapling** | Web server sends queries to OCSP Responder at regular intervals; includes signed, time-stamped response in handshake with browser |

#### Web Browser Certificate Revocation

| Browser | Procedure | Description |
|---------|-----------|-------------|
| **Chrome** | CRLSet | List of revoked certificates from CAs pushed as software update |
| **Firefox** | OneCRL | List of revoked intermediate certificates pushed in updates; can query OCSP |
| **Safari** | (No name) | Collects revoked certificates from CAs; periodically retrieved by Apple devices |
| **Edge** | CRLSet | Windows OS checks for server certificate revocation |

### Types of Digital Certificates

#### Root Digital Certificates
- Created and verified by a CA; **self-signed** (no higher authority)
- **Certificate chaining**: path between trusted root CAs and intermediate CAs
- Each certificate signed by the next higher certified entity in the chain
- **Root of trust**: trust can be traced back to the highest level of CA

#### Distribution Methods
- **OS updates**: trusted root CAs, intermediate CAs, untrusted certificates distributed through OS updates
- **Web browser updates**: many browsers now rely on their own updates
- **Pinning**: digital certificate hard-coded within the app or program using it

#### Domain Digital Certificates
- Web server digital certificates perform two functions: ensure authenticity of web server and cryptographic connection
- **Key exchange** (TLS handshake):
  1. Browser sends "ClientHello" with supported cryptographic algorithms
  2. Server responds with "ServerHello" and sends server digital certificate
  3. Browser verifies certificate, extracts public key, generates pre-master secret, encrypts with server's public key
  4. Server decrypts; both create master secret → session keys for symmetric encryption

#### Certificate Types

| Type | Description |
|------|-------------|
| **Domain Validation (DV)** | Verifies entity has control over domain name; does not indicate trustworthiness |
| **Organization Validation (OV)** | More extensive verification of business legitimacy |
| **Extended Validation (EV)** | Requires extensive verification of business legitimacy |
| **Wildcard certificate** | Validates main domain plus all subdomains |
| **SAN (Subject Alternative Name)** | Allows different values on single certificate; covers multiple IP addresses |
| **Code signing** | Signs software to verify publisher identity |
| **Self-signed** | Signed by entity itself; not from trusted CA |

---

## Objective 2 - Public Key Infrastructure (PKI)

### What Is PKI?
- **PKI**: underlying infrastructure serving as a key management system for controlling public keys, private keys, and digital certificates
- Set of software, hardware, processes, procedures, and policies needed to create, manage, distribute, use, store, and revoke digital certificates across large user populations
- Goal: establish identity of people, devices, and services to control access, protect data, provide accountability
- **PKI = digital certificate management at scale**

### Trust Models

| Trust Model | Description | Use Case |
|-------------|-------------|----------|
| **Direct trust** | Relationship exists because one person knows the other | Alice personally gives Bob her certificate |
| **Third-party trust** | Two individuals trust each other because both trust a common third party | Courtroom: both parties trust the judge |
| **Web of trust** | Each user signs and exchanges certificates with all other users; based on direct trust | Less secure; no third party |

#### PKI Trust Models

| Model | Description | Limitations |
|-------|-------------|-------------|
| **Hierarchical** | Single hierarchy with one master CA (root) signing all certificates | Single key compromise = all certificates worthless; single CA bottleneck |
| **Distributed (mesh)** | Multiple CAs sign digital certificates; can delegate to intermediate CAs | Basis for most Internet certificates; eliminates single points of failure |
| **Bridge** | One CA acts as facilitator/hub interconnecting all other CAs; does not issue certificates | Links different trust models together |

### Managing PKI

#### Certificate Policy (CP)
- Published set of rules governing PKI operation
- Provides recommended baseline security requirements for CA, intermediate CA, and other PKI components

#### Certificate Practice Statement (CPS)
- More technical document than CP
- Describes in detail how CA uses and manages certificates
- Covers: end-user registration, certificate issuance, revocation, procedural controls, key pair generation, private key protection

#### Certificate Life Cycle

| Stage | Description |
|-------|-------------|
| **Creation** | Certificate created and issued; user positively identified; CA applies signing key; forwarded to registration authority |
| **Suspension** | Temporary suspension of certificate validity (e.g., employee leave of absence); can be reinstated |
| **Revocation** | Certificate no longer valid; may be revoked before expiration (e.g., private key compromised); CA updates CRL |
| **Expiration** | Certificate can no longer be used; user must follow process for new certificate |

### Key Management

#### Key Storage
- **Public keys**: embedded within digital certificates
- **Private keys**: stored on user's local system; software-based storage vulnerable to attacks
- **Hardware storage**: smart cards, tokens, special CA root/intermediate CA hardware devices
- **Never share keys in plaintext; store in password-protected/encrypted files; don't copy; destroy expired keys**

#### Key Usage
- Multiple pairs of dual keys for different purposes (e.g., one pair for encryption, one for digital signatures)

#### Key Handling Procedures

| Procedure | Description |
|-----------|-------------|
| **Escrow** | Keys managed by third party; private key split, each half encrypted, stored separately; user retrieves halves and combines |
| **Expiration** | Keys cease functioning after set period; prevents indefinite decryption by attacker with stolen key |
| **Renewal** | Existing keys continue to be used; new keys not generated; continual renewal increases vulnerability |
| **Revocation** | Key permanently invalid before expiration (e.g., employee terminated); cannot be reinstated |
| **Recovery** | Key recovery agent (KRA) designated; or M-of-N control: key divided into parts distributed to N people, M must agree to recover |
| **Suspension** | Temporary suspension (set period); can be reinstated; CA notified and CRL checked |
| **Destruction** | Removes all private/public keys and user identification from CA; revoked/expired info remains for audit |

---

## Objective 3 - Secure Communication and Transport Protocols

### Tunneling Concept
- **Tunneling**: transporting data securely across a network
- Data is first encrypted, then **encapsulated** (enclosed with additional header for routing)
- Encapsulation adds unencrypted header so routers can forward packets

### Transport Layer Security (TLS)
- Replacement for **SSL** (Secure Sockets Layer, developed 1994 by Netscape); SSL is deprecated
- Current version: **TLS v1.3** — removes MD5/SHA-224 support, requires Perfect Forward Secrecy, encrypts handshake messages
- **Cipher suite**: named combination of encryption, authentication, and MAC algorithms negotiated during handshake
- Example: `TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256` = TLS protocol, ECDHE key exchange, AES-128-GCM encryption, SHA-256 hashing

### IP Security (IPSec)
- Suite of protocols for securing IP communications; encrypts and authenticates each IP packet
- **Transparent** to applications, users, and software
- Three areas of protection:

| Protection | Protocol | Description |
|-----------|----------|-------------|
| **Authentication** | Authentication Header (AH) | Verifies packets received were sent from source |
| **Confidentiality** | Encapsulating Security Payload (ESP) | Encrypts packets; supports sender authentication |
| **Key management** | ISAKMP/Oakley | Generates keys and authenticates users via digital certificates |

#### IPSec Modes

| Mode | Description | Use Case |
|------|-------------|----------|
| **Transport** | Encrypts only data portion (payload); header unencrypted | When device must see source/destination addresses |
| **Tunnel** | Encrypts both header and data portion | Network-to-network communication |

#### IPSec vs TLS

| Feature | IPSec | TLS |
|---------|-------|-----|
| OSI layer | Layer 3 | Layers 4-7 |
| Installation | Generic; requires full client on device | Vendor specific; built into web browsers |
| Configuration | Complex | Basic |
| Protections | All IP-based applications | Web apps, file sharing, email |

#### IPSec Architectures
- **Devices**: install on all devices (highest security) or only on routers
- **Integration into TCP/IP**: IPv6 has IPSec integrated; IPv4 requires changes
- **BITS (bump in the stack)**: separate layer between IP and Data Link layer
- **BITW (bump in the wire)**: hardware device providing IPSec services

### Other Secure Protocols

| Protocol | Description | Port/Use |
|----------|-------------|----------|
| **HTTPS** | HTTP over TLS/SSL; most common web security | Port 443 |
| **SSH** | Encrypted alternative to Telnet; Linux/UNIX remote access | Digital certificate authentication |
| **S/MIME** | Securing email messages; encryption + digital signatures | Email encryption |
| **SRTP** | Secure extension of RTP; protects VoIP communications | Voice over IP |

---

## Objective 4 - Implementing Cryptography

### Key Strength
- **Key**: random string of bits serving as input parameter for cryptographic algorithms
- **Key ≠ password**: passwords are for human memory; keys are for hardware/software

#### Three Characteristics of Key Strength

| Characteristic | Description |
|---------------|-------------|
| **Randomness** | Must be random with no predictable pattern |
| **Cryptoperiod** | Length of time for which a key is authorized for use; limited period protects from extended cryptanalysis |
| **Key length** | Shorter keys broken more easily; key space = all possible values for a key |

- Formula: character-set^key-length = key space
- Example: 3-character key with 26-letter alphabet = 26^3 = 17,576 possible keys
- Increasing key length from 3 to 4 increases key space from 17,576 to 456,976
- On average, half the key space must be searched to find the key

### Secret Algorithms
- **Secret algorithms are weak** — Kerckhoffs's Principle (1883): systems should not require secrecy
- Algorithms should be public; only keys should be private
- Proprietary algorithms cannot be properly analyzed since they're kept secret
- Modern algorithms selected by competition after thorough vetting by cryptographic community

### Block Cipher Modes of Operation

| Mode | Description | Security |
|------|-------------|----------|
| **ECB (Electronic Code Book)** | Most basic; each block encrypted separately; identical plaintext → identical ciphertext | Not suitable for use |
| **CBC (Cipher Block Chaining)** | Each ciphertext block fed back into encryption; each plaintext block XORed with previous ciphertext block | Much more difficult to break |
| **CTR (Counter)** | Sender and receiver access a counter computing new value each exchange | Requires synchronous counter |
| **GCM (Galois/Counter)** | Encrypts plaintext + computes MAC; uses counter + AAD (additional authentication data) | Provides both encryption and authentication |

---

## Key Terms

- **Asymmetric cryptography** — uses two mathematically related keys
- **Certificate authority (CA)** — party responsible for digital certificates
- **Certificate chaining** — linking certificates to establish trust
- **Certificate practice statement (CPS)** — technical document describing how CA manages certificates
- **Certificate policy (CP)** — published rules governing PKI operation
- **Certificate revocation list (CRL)** — list of revoked certificate serial numbers
- **Certificate signing request (CSR)** — formal request for digital certificate
- **Cipher suite** — named combination of encryption, authentication, and MAC algorithms
- **Cryptoperiod** — length of time a key is authorized for use
- **Digital certificate** — technology associating user identity to public key, signed by trusted third party
- **Digital signature** — electronic verification of sender
- **Domain validation (DV)** — certificate verifying control over domain name
- **Encapsulation** — enclosing encrypted data with additional header for routing
- **Encapsulating Security Payload (ESP)** — IPSec protocol for confidentiality
- **Extended Validation (EV)** — certificate requiring extensive business verification
- **Galois/Counter (GCM)** — block cipher mode providing encryption and authentication
- **HTTPS** — HTTP over TLS/SSL on port 443
- **Intermediate certificate authority** — processes CSRs on behalf of CA
- **IPSec** — suite of protocols for securing IP communications
- **Key escrow** — third-party management of keys
- **Key length** — number of bits in a cryptographic key
- **Key space** — all possible values for a specific key
- **OCSP** — Online Certificate Status Protocol for real-time certificate status
- **OCSP stapling** — web server includes OCSP response in TLS handshake
- **PKI (Public Key Infrastructure)** — certificate management at scale
- **Root digital certificate** — self-signed certificate created and verified by CA
- **Self-signed certificate** — signed by entity itself, not from trusted CA
- **Subject Alternative Name (SAN)** — allows different values on single certificate
- **TLS (Transport Layer Security)** — secure protocol replacing SSL
- **Tunneling** — transporting data securely across a network via encapsulation
- **Wildcard certificate** — validates main domain plus all subdomains

---

## Review Questions

1. Which element of a digital certificate provides proof of the genuineness of the owner?
   - a. Serial number
   - b. Digital signature of the issuer
   - c. Expiration date
   - d. Owner's public key

2. What process is used to request a digital certificate?
   - a. CSR generation
   - b. Certificate revocation
   - c. Key exchange
   - d. OCSP stapling

3. Which method performs a real-time lookup of a certificate's status?
   - a. CRL
   - b. OCSP
   - c. Pinning
   - d. Certificate chaining

4. What is the beginning point of a certificate chain?
   - a. Intermediate certificate
   - b. User digital certificate
   - c. Root digital certificate
   - d. Registration authority

5. Which trust model has multiple CAs that sign digital certificates?
   - a. Hierarchical
   - b. Distributed
   - c. Bridge
   - d. Web of trust

6. Which is NOT part of the certificate life cycle?
   - a. Creation
   - b. Suspension
   - c. Encryption
   - d. Expiration

7. What is M-of-N control?
   - a. A method of encrypting messages with multiple keys
   - b. A method of dividing a private key into parts requiring a subset to recover
   - c. A method of distributing certificates to multiple users
   - d. A method of revoking certificates

8. Which IPSec protocol provides confidentiality?
   - a. AH
   - b. ESP
   - c. ISAKMP
   - d. Oakley

9. What is the difference between IPSec transport and tunnel modes?
   - a. Transport encrypts entire packet; tunnel encrypts only payload
   - b. Transport encrypts only payload; tunnel encrypts entire packet
   - c. Transport is for network-to-network; tunnel is for device-to-device
   - d. Transport uses AH; tunnel uses ESP

10. Which protocol is used to secure VoIP communications?
    - a. SSH
    - b. S/MIME
    - c. SRTP
    - d. HTTPS

11. What determines the strength of a cryptographic key?
    - a. Randomness, cryptoperiod, and key length
    - b. Algorithm type and block size
    - c. Number of users and certificate chain length
    - d. Encryption speed and decryption complexity

12. What is Kerckhoffs's Principle?
    - a. Systems should keep algorithms secret for maximum security
    - b. Systems should not require secrecy; algorithms should be public
    - c. Keys should be stored in plain text for easy access
    - d. Digital certificates should be self-signed

13. Which block cipher mode is NOT considered suitable for use?
    - a. CBC
    - b. GCM
    - c. ECB
    - d. CTR
