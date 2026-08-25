---
created: 2026-08-19 20:12:00
class:
  - document
description: CompTIA Security+ SY0-701 Module 3 — cryptography fundamentals, algorithms, uses, limitations, and attacks
mod.: 2026-08-19 20:12:00
aliases:
  - security+ module 3
  - cryptography fundamentals
tags:
  - study/security-plus
  - study/security-plus/module-3
---

# Module 3 - Fundamentals of Cryptography

## Objectives

1. [[#Objective 1 - Defining Cryptography|Define cryptography]]
2. [[#Objective 2 - Cryptographic Algorithms|Describe hash, symmetric, and asymmetric cryptographic algorithms]]
3. [[#Objective 3 - Using Cryptography|List the various ways in which cryptography is used]]
4. [[#Objective 4 - Cryptographic Limitations and Attacks|Explain different cryptographic limitations and attacks]]

---

## Objective 1 - Defining Cryptography

### Steganography: Hiding the Message
- **Steganography**: hiding the very existence of a message or information (Greek: "covered writing")
- Ancient Greeks used techniques like writing on wax-covered tablets, tattoos, and hiding messages in sandals
- Modern steganography hides data in harmless image, audio, or video files by dividing data into small pieces among invisible portions (metadata, header fields, content areas)
- **Obfuscation**: making something obscure or unclear; steganography, data masking, and tokenization are all forms of obfuscation

### Cryptography: Hiding the Meaning
- **Cryptography**: practice of transforming ("scrambling") information so its meaning cannot be understood by unauthorized parties but can only be understood by approved recipients (Greek: "hidden writing")
- Two basic methods dating back to ancient times:
  - **Transposition**: rearranging each letter of the message (e.g., "ran" → "arn")
  - **Substitution**: replacing one letter for another (e.g., ROT13, XOR cipher)

#### Key Terminology

| Term | Definition |
|------|-----------|
| **Plaintext** | Unencrypted data input for encryption or output of decryption |
| **Ciphertext** | Scrambled, unreadable output of encryption |
| **Cleartext** | Unencrypted data not intended to be encrypted ("in the clear") |
| **Encryption algorithm (cipher)** | Procedures based on mathematical formula |
| **Key** | Mathematical value entered into algorithm to produce ciphertext |
| **Encryption** | Changing plaintext into ciphertext |
| **Decryption** | Changing ciphertext back to plaintext |

- **Critical factor**: algorithms are designed to be public and well-known; the **key** must always be kept secret

### Benefits of Cryptography
- Provides protections to data in all three states: **data at rest**, **data in use**, and **data in transit**
- Considered both a **mitigation technique** (reducing vulnerability/severity) and a **hardening technique** (making systems more resilient)

| Protection | Description |
|-----------|-------------|
| **Confidentiality** | Only authorized parties can view the information; encrypted info viewable only by those with the key |
| **Integrity** | Information is correct and unaltered; encrypted info cannot be changed except by authorized users with the key |
| **Authentication** | Proof of genuineness of the sender; prevents impersonation |
| **Nonrepudiation** | Inability to deny performing an action; prevents fraudulently reneging on transactions |
| **Obfuscation** | Makes something obscure; encryption obfuscates data based on a secret key |

- **Security through obscurity** is flawed — relying solely on keeping something hidden is not a viable security strategy
- **Proprietary cryptographic algorithms are weak** — modern algorithms are based on known mathematical proofs and selected by competition after thorough vetting

---

## Objective 2 - Cryptographic Algorithms

### Variations of Algorithms

#### Cipher Machines versus Computers
- Historical cipher machines: cipher disk (1470), **Enigma machine** (WWII, Germany)
- **One-time pad (OTP)**: combines plaintext with random key; the only encryption method that cannot be broken mathematically; used by intelligence agencies during Cold War

#### Stream versus Block Ciphers

| Type | Description | Security |
|------|-------------|----------|
| **Stream cipher** | Takes one character and replaces it with one character | Less secure (engine doesn't vary) |
| **Block cipher** | Manipulates an entire block of plaintext at once (8-16 bytes) | More secure (output more random, reset after each block) |
| **Sponge function** | Takes input of any length, returns output of any requested length; repeatedly "absorbs" input padded with characters | Newer approach |

### Hash Algorithms
- **One-way algorithm** — cannot be reversed to reveal original data
- **Hashing**: creates unique "digital fingerprint" (digest/message digest) of a set of data
- Used primarily for **integrity** and **comparison purposes**, not encryption

#### Characteristics of Secure Hash Algorithms

| Characteristic | Description |
|---------------|-------------|
| **Fixed size** | Digest of short data same size as digest of long data |
| **Unique** | Two different data sets cannot produce same digest |
| **Original** | Cannot produce data set with a desired/predefined hash |
| **Secure** | Resulting hash cannot be reversed to determine original plaintext |

#### Common Hash Algorithms

| Algorithm | Notes |
|-----------|-------|
| **MD5** | Early hash; serious weaknesses identified; no longer suitable for use |
| **SHA-1** | Developed 1993; no longer suitable for use |
| **SHA-2** (SHA-256, SHA-384, SHA-512) | Currently secure; number indicates digest length in bits |
| **SHA-3** | Announced 2015 after 8-year competition; designed to be dissimilar to earlier hashes |
| **RipeMD** (160, 256, 320) | Two independent parallel chains of computation combined at end |
| **Whirlpool** | 512-bit digest; never patented; free for any use |

### Symmetric Cryptographic Algorithms
- **Symmetric cryptography (private key cryptography)**: uses the same key to encrypt and decrypt
- Protects **confidentiality** of data
- Key must be kept secret; primary challenge is **distributing and maintaining** the key securely among multiple users

#### Common Symmetric Algorithms

| Algorithm | Description |
|-----------|-------------|
| **AES (Advanced Encryption Standard)** | 128-bit blocks; 128/192/256-bit keys performing 9/11/13 rounds; no successful attacks to date |
| **Blowfish** | 64-bit blocks; 32-448 bit keys; no significant weaknesses identified |
| **Twofish** | Later derivation of Blowfish; considered strong but less widely used |
| **DES** | Deprecated — no longer secure |
| **3DES** | Deprecated — no longer secure |
| **RC4** | Deprecated — no longer secure |

### Asymmetric Cryptographic Algorithms
- **Asymmetric cryptography (public key cryptography)**: uses two mathematically related keys — **public key** (freely distributed) and **private key** (known only to owner)
- Protects **confidentiality** of data
- Solves key distribution problem of symmetric encryption

#### Key Principles
- **Key pairs**: requires a pair of keys (public + private)
- **Public key**: designed to be public; can be freely given to anyone
- **Private key**: must be kept confidential; never shared
- **Both directions**: document encrypted with public key decrypted with private key, and vice versa

#### Common Asymmetric Algorithms

| Algorithm | Description |
|-----------|-------------|
| **RSA** | Published 1977; based on factoring large prime numbers; public key (n,e) private key (n,d) |
| **ECC (Elliptic Curve Cryptography)** | Based on elliptic curves instead of factoring; smaller key sizes, faster computations, lower power consumption; used by U.S. government, Tor, Bitcoin |
| **DSA (Digital Signature Algorithm)** | U.S. government standard for digital signatures; proposed by NIST in 1991 |
| **Diffie-Hellman** | Key exchange algorithm |

#### RSA vs ECC Key Length Comparison

| RSA Key Length | ECC Key Length | Same Security Level |
|---------------|---------------|-------------------|
| 1024 | 160 | Equivalent |
| 2048 | 224 | Equivalent |
| 3072 | 256 | Equivalent |
| 7680 | 384 | Equivalent |
| 15360 | 521 | Equivalent |

#### Digital Signatures
- **Digital signature**: electronic verification of the sender; uses asymmetric keys in both directions
- Benefits: verify sender, prevent disowning (nonrepudiation), prove message integrity
- Process: Bob creates digest → encrypts digest with his private (= digital signature) → sends memo + signature → Alice decrypts with Bob's public key → compares digests
- **DSA**: U.S. government standard; proposed by NIST in 1991 for Digital Signature Standard (DSS)

#### Key Exchange Practices

| Action | Whose Key | Which Key |
|--------|-----------|-----------|
| Send encrypted message | Recipient's key | Public key |
| Read encrypted message | Own key | Private key |
| Encrypt copy for self | Own key | Public key to encrypt |
| Read received reply | Own key | Private key |
| Forward to someone else | Forward recipient's key | Public key |

---

## Objective 3 - Using Cryptography

### Encryption through Software

#### File and File System Cryptography
- **File-level encryption**: encrypt/decrypt files one by one
- **Third-party software**: GnuPG, AxCrypt, Folder Lock, VeraCrypt
- **OS native encryption**: Microsoft EFS (Encrypting File System), Apple FileVault

#### Disk Encryption
- **Full-disk encryption (FDE)**: protects all data on drive including installed OS (e.g., BitLocker)
- **Volume-level encryption**: applies to a section of drive with a file system
- **Partition-level encryption**: depends on if partition is formatted and contains file system

#### Database Encryption
- **Transparent data encryption (TDE)**: executes encryption/decryption within database engine itself; no additional packages needed
- **Plugin method**: attaches encryption module to DBMS
- Encryption levels: database file, table, column, record-level, cell-level (higher granularity = more key management + performance tax)

### Hardware Encryption
- Cannot be exploited like software encryption

| Hardware Type | Description |
|--------------|-------------|
| **USB devices** | Cryptographic features built into hardware; automatic encryption of written data; remote disable/self-destruct capabilities |
| **Self-encrypting drives (SEDs)** | Protect all data written; authentication on power-up; can perform cryptographic erase on failure |
| **Hardware security module (HSM)** | Removable external cryptographic device; onboard random number generator, key storage, accelerated encryption; cannot be compromised by malware |
| **Trusted Execution Environment (TEE)** | Secure cryptoprocessor internal to computer; hardware-based, tamper-resistant |
| **Trusted Platform Module (TPM)** | International standard for cryptoprocessors; random number generator, asymmetric encryption, startup integrity checks; TPM v2.0 required for Windows 11 |
| **Secure enclave** | Apple/Android equivalent of TPM |

### Blockchain
- **Blockchain**: shared, immutable ledger facilitating recording transactions and tracking assets in a business network
- Records maintained across several computers linked in peer-to-peer network
- Relies on cryptographic hash algorithms (notably SHA-256)

| Type | Description |
|------|-------------|
| **Public blockchain** | Anyone can join; used for cryptocurrencies and crypto mining |
| **Private blockchain** | Closed network for enterprise internal use |
| **Federated (consortium) blockchain** | Multiple organizations with preselected nodes for reading, writing, auditing |

---

## Objective 4 - Cryptographic Limitations and Attacks

### Limitations of Cryptography
- **Resource versus security constraint**: tug-of-war between available resources (time, energy) and security provided
- Low-power devices (sensors, IoT) draw as little as 0.001 watt vs laptop's 60 watts
- Cryptographic algorithms require time and energy in short supply for these devices

#### Cryptographic Constraints

| Limitation | Explanation |
|-----------|-------------|
| **Speed** | Encryption/decryption speed depends on hardware and software factors |
| **Size** | Encrypted file can be up to one-third larger than plaintext |
| **Weak keys** | Some ciphers produce keys causing unpredictable behavior |
| **Key length** | Short key length results in weaker security |
| **Longevity** | More powerful computers can crack keys faster |
| **Predictability** | Weak random number generators create predictable output |
| **Reuse** | Reusing same key provides larger data footprint for attackers |
| **Entropy** | Low entropy allows prediction of future-generated values |
| **Computational overhead** | IoT devices often lack capacity for cryptographic overhead |

### Attacks on Cryptography

#### Algorithm Attacks

| Attack Type | Description |
|------------|-------------|
| **Known ciphertext attack** | Statistical tools analyze ciphertext to discover patterns revealing plaintext or key |
| **Downgrade attack** | Attacker forces system to abandon higher security mode and fall back to older, less secure mode |
| **Misconfiguration attacks** | Incorrect choices or misconfigurations of cryptography options (most common breach cause) |

#### Collision Attacks
- **Collision**: two files producing the same hash digest
- **Collision attack**: attempting to find two input strings that produce same hash result
- **Birthday attack**: based on birthday paradox; makes finding collisions easier (23 people needed for >50% chance of shared birthday vs 253 for matching specific birthday)

#### Quantum Computing
- **Quantum computing**: uses atomic-scale units (qubits) that can be both 0 and 1 simultaneously
- Much faster and more efficient than classical computers
- **Risk to cryptography**: could factor large prime numbers quickly, rendering virtually all current asymmetric algorithms useless
- **Post-quantum cryptography**: new encryption proposals being developed that are "quantum-safe"
- Timeline debated: some say 10 years, others 30+ years

---

## Key Terms

- **Algorithm** — mathematical procedures for encryption/decryption
- **Asymmetric cryptographic algorithm** — uses two mathematically related keys (public and private)
- **Birthday attack** — statistical technique making collision attacks easier
- **Blockchain** — shared, immutable distributed ledger
- **Collision** — two files producing the same hash digest
- **Cryptography** — practice of transforming information to prevent unauthorized understanding
- **Database-level encryption** — applying cryptography to a database
- **Decryption** — changing ciphertext back to plaintext
- **Digital signature** — electronic verification of sender using asymmetric cryptography
- **Downgrade attack** — forcing system to fall back to less secure mode
- **Encryption** — changing plaintext into ciphertext
- **File-level encryption** — encrypting individual files
- **Full-disk encryption (FDE)** — encrypting entire drive including OS
- **Hardware security module (HSM)** — removable external cryptographic device
- **Hashing** — creating unique digital fingerprint of data
- **Key exchange** — process of sharing cryptographic keys securely
- **Key length** — number of bits in a cryptographic key
- **Nonrepudiation** — inability to deny performing an action
- **Open public ledger** — public blockchain anyone can join
- **Partition-level encryption** — encryption applied to drive partitions
- **Record-level encryption** — encryption at individual record level
- **Secure enclave** — Apple/Android cryptoprocessor equivalent to TPM
- **Steganography** — hiding existence of information
- **Symmetric cryptographic algorithm** — uses single key for encryption and decryption
- **Trusted Platform Module (TPM)** — international standard for cryptoprocessors
- **Volume-level encryption** — encryption applied to drive volumes

---

## Review Questions

1. Aaliyah wants to send a message without anyone knowing she is communicating with the recipient. Which technique would she use?
   - a. Cryptography
   - b. Steganography
   - c. Encryption
   - d. Ciphering

2. Zeinab's customer claims they never received notification of terms of service changes. An automated "read receipt" shows the customer opened the email. What action will Zeinab take?
   - a. Repudiation
   - b. Obfuscation
   - c. Integrity
   - d. Nonrepudiation

3. Which of the following is NOT a form of obfuscation?
   - a. Tokenization
   - b. Ciphering
   - c. Steganography
   - d. Data masking

4. Which of the following is NOT correct about "security through obscurity"?
   - a. It attempts to hide its existence from outsiders
   - b. Proprietary cryptographic algorithms are a common example
   - c. It is essentially impossible to achieve
   - d. It should only be used as a general information security protection in extreme circumstances

5. Layla has encrypted a document so only those with the key can view it. What protection has she provided?
   - a. Confidentiality
   - b. Integrity
   - c. Authentication
   - d. Obfuscation

6. Which of the following is NOT correct about an OTP?
   - a. It combines plaintext with a random key
   - b. The recipient must have a copy of the pad to decrypt
   - c. It was used during the Cold War
   - d. It requires a cipher disk

7. What is data called that is input into a cryptographic algorithm for encryption?
   - a. Plaintext
   - b. Byte-text
   - c. Cleartext
   - d. Ciphertext

8. Which creates the most secure ciphertext?
   - a. Redundant function
   - b. Stream cipher
   - c. Block cipher
   - d. Sponge function

9. Which hash algorithm produces the longest and most secure digest?
   - a. RipeMD160
   - b. SHA-256
   - c. SHA3-512
   - d. Whirlpool

10. Which algorithm uses the same key to both encrypt and decrypt data?
    - a. Asymmetric cryptographic algorithm
    - b. Hashing algorithm
    - c. Pairwise keypair algorithm
    - d. Symmetric cryptographic algorithm

11. Which is NOT to be decrypted but only used for comparison purposes?
    - a. Digest
    - b. Key
    - c. Stream
    - d. Algorithm

12. Which is NOT a characteristic of a secure hash algorithm?
    - a. Collisions may occur, but they are rare
    - b. A message cannot be produced from a predefined hash
    - c. The hash should always be the same fixed size
    - d. The results of a hash function should not be reversed

13. Which is a weakness of RSA?
    - a. RSA weaknesses are based on ECC
    - b. RSA has no known weaknesses
    - c. As computers become more powerful, the ability to compute factoring has increased
    - d. The digest produced by the RSA algorithm is too short to be secure
