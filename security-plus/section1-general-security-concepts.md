# Section 1 — General Security Concepts
**Exam weight: 12%**

---

## 1.1 Security Controls
**Video length: 11:48**

### Key Concepts
- **Control Types:**
    - **Technical** - OS controls
    - **Managerial** - Security policy, company rules, standards
    - **Operational** - Personnel rules, professional development, guards
    - **Physical** - Limits physical access, locks, card readers
- **Usages:**
    - **Preventative** - Works *before* an event to limit access and prevent incidents
    - **Deterrent** - Works *before* an event to discourage malicious behavior
    - **Detective** - Works *during* an event to identify current exploits or attack attempts
    - **Corrective** - Works *after* an event to fix damage, reverse attack impact, and reduce downtime
    - **Directive** - Works *ongoing* to inform and guide behavior through policy and training

### Notes
| Control Types | Preventative | Deterrent | Detective | Corrective | Compensating | Directive |
|---|---|---|---|---|---|---|
| **Technical** | Firewall | Splash Screen | System Logs | Back-Ups | Firewall until Patch | Store as Encrypted |
| **Managerial** | Security Policy | Demotion | Review Login Reports | Security Alert | Separate Duties | Compliance Policy |
| **Operational** | Guard Shack | Reception Desk | Property Patrol | Law Enforcement | Policy Training | |
| **Physical** | Locks | Warning Signs | Motion Sensors | Fire Extinguisher | Back-up Generators | Authorized Personnel Signs |

---

## 1.2 Security Concepts

---

### The CIA Triad
**Video length: 5:17**

### Key Concepts
- **Confidentiality** - Ensures only authorized individuals can access data (Access Controls, Encryption, Authentication)
- **Integrity** - Ensures information is not altered in transit or storage (Hashing, Signatures, Certificates, Non-Repudiation)
- **Availability** - Ensures systems are operational and accessible when needed (Redundancy, Fault Tolerance, Patching)

### Notes
- A core goal of cybersecurity is maintaining a strong balance of all three elements of the **CIA Triad**, as weakening any one element undermines overall security

---

### Non-Repudiation
**Video length: 7:57**

### Key Concepts
- **Non-Repudiation** - Ensures the sender cannot deny sending a message and that the message was not altered
- **Hash** - A fixed-length string of characters that uniquely represents a specific set of data
- **Private Key** - An encryption key known only to the owner
- **Public Key** - An encryption key shared openly with others
- **Digital Signature** - A hash of the plaintext encrypted with the sender's private key, sent alongside the plaintext to verify identity and integrity

### Notes
- Non-repudiation works like a signed contract: what was sent is provably what was sent
- Proof of integrity means Sent = Received
- A **hash** verifies data integrity by comparing the hash before and after transmission; any change in data produces a completely different hash
- A **digital signature** is verified by the receiver using the sender's **public key**, confirming both the sender's identity and that the data was not altered in transit

---

### Authentication, Authorization, and Accounting
**Video length: 9:03**

### Key Concepts
- **Identification** - Who you claim to be (username)
- **Authentication** - Proof that you are who you claim to be (password, biometric, certificate)
- **Authorization** - Based on verified identity, determines what resources you can access
- **Accounting** - A log of login/logout times, data sent and received, and actions taken
- **Certificate** - An electronic credential issued by a **Certificate Authority (CA)** that verifies a device or user's identity

### Notes
- AAA server network traffic example:
    - Client > Internet > Firewall > AAA Server (authentication check) > File Server (if approved)
- Devices can be authenticated using a **digital certificate**, commonly deployed on company-owned devices
- A **Certificate Authority (CA)** issues and manages certificates; most medium to large organizations maintain their own internal CA
- **Authorization models** such as roles and permission lists make it practical to manage access at scale
- **Abstraction** assigns permissions to roles or groups rather than individuals, so a user inherits permissions by being added to a group

---

### Gap Analysis
**Video length: 6:44**

### Key Concepts
- **Gap** - The difference between where a company's security currently is and where it needs to be
- **Gap Framework (Baseline)** - A standard used to measure security posture; can be a widely adopted framework or one specific to the organization
- **Gap Analysis Report** - The final deliverable of a gap analysis; documents the current state, identifies shortfalls, and provides a recommended path forward

### Notes
- A thorough gap analysis requires long-term research into the organization's existing security posture
- Common gap frameworks:
    - **NIST Publication 800-171** - Protecting controlled unclassified information in federal systems
    - **ISO/IEC 27001** - International standard for information security management systems
- Analysis compares existing policy and implementation against the chosen baseline, working from broad categories down to specific controls
- Reports often include charts and visual aids to make findings accessible to non-technical stakeholders

---

### Zero Trust
**Video length: 10:04**

### Key Concepts
- **Zero Trust** - A security model where no user, device, or system is trusted by default; every access request must be verified
- **Planes of Operation** - A way of logically dividing network functions into separate layers
- **Data Plane** - Handles the actual forwarding of frames and packets between interfaces using hardware
- **Control Plane** - Makes decisions about how traffic should be handled; defines policies, builds routing tables, manages ACLs
- **Threat Scope Reduction** - Minimizing the number of entry points into a system or network to reduce attack surface
- **Security Zones** - Network segments categorized by trust level (trusted, untrusted); used to enforce access boundaries
- **Policy Enforcement Point (PEP)** - The gatekeeper that all traffic passes through on the data plane; collects information about source, destination, and traffic type
- **Policy Decision Point (PDP)** - The control plane component that decides whether to grant or deny access, made up of two parts:
    - **Engine** - Evaluates authentication and applies policies to grant, deny, or revoke access
    - **Administrator** - Instructs the PEP based on the engine's decision; generates and passes credentials

### Notes
- Every access attempt must be verified regardless of origin: MFA, device certificates, system permissions, and continuous monitoring all apply
- Splitting network functions into **planes of operation** introduces logical segmentation without requiring physical separation
- **Adaptive identity** evaluates multiple factors (source IP, device type, user relationship to the organization, connection type) to make access decisions more dynamic
- **Policy-driven access controls** combine verified identity with defined rules to grant the minimum necessary access
- **Security zones** function similarly to VLANs or department groups, creating implicit trust within a zone while restricting cross-zone access by default

---

### Physical Security
**Video length: 8:17**

### Key Concepts
- **Physical Security** - Controls and measures designed to prevent or deter unauthorized personnel from accessing physical locations and hardware

### Notes
- **Access control vestibules** are enclosed entry areas where only one door can open at a time, forcing individuals through a controlled checkpoint using cards, biometrics, or a guard
- **Fencing** establishes a hard perimeter; effective but visible; design should account for climbing prevention
- **Video surveillance (CCTV)** reduces the need for personnel; can integrate motion detection and object recognition across a networked system
- **Security guards** are most effective when deployed in pairs to provide checks and balances
- **ID badges** serve as both identification and access control when integrated with electronic locks
- **Lighting** is a low-cost deterrent; well-lit areas eliminate cover for unauthorized entry
- **Sensors:**
    - **Infrared** - Detects motion or body heat; used in motion detectors and pressure sensors
    - **Microwave** - Covers larger areas than infrared; detects movement through walls
    - **Ultrasonic** - Emits sound waves and detects movement based on reflected signals; used for close-range detection

---

### Deception and Disruption
**Video length: 4:30**

### Key Concepts
- **Honeypot** - A decoy system intentionally left exposed to attract attackers, observe their techniques, and gather intelligence

### Notes
- **Honeynets** are collections of multiple honeypot devices designed to simulate a believable network environment
- **Honey files** are fake documents placed to bait attackers; most useful when paired with access alerts that trigger when the file is opened
- **Honey tokens** are traceable pieces of data (fake credentials, tracking pixels, cookies) embedded in systems or files; if exfiltrated, they reveal where the breach originated

---

## 1.3 Change Management

---

### Change Management
**Video length: 11:22**

### Key Concepts
- **Change Management** - A structured process for planning, approving, and implementing changes to IT systems
- **Change** - Any modification to IT systems including software upgrades, hardware replacements, patches, or configuration changes
- **Stakeholder** - Any person or group affected by a change; stakeholders often have input on timing and scope

### Notes
- A **change approval request form** is required for significant changes and typically includes:
    - Purpose of the change
    - Scope, scheduled date, and time
    - Systems affected and risks of both making and not making the change
    - Sign-off from the **change control board**
- **Impact analysis** assesses whether a change could break dependent systems or introduce new vulnerabilities
- Changes should be tested in a **sandbox environment** such as a VM before being pushed to production
- A **rollback plan** must always be prepared so the previous state can be restored if something goes wrong
- A **maintenance window** should be scheduled during off-peak hours to minimize disruption; holidays and peak business periods should be avoided
- Change management procedures should be documented in a **standard operating document** to ensure consistency across the organization

---

### Technical Change Management
**Video length: 10:54**

### Key Concepts
- **Scope** - The defined boundary of what a change covers; set by the change control board and must not be exceeded without approval
- **Downtime** - The period during which a system is unavailable; must be planned for and minimized
- **Legacy Applications** - Older systems that are no longer actively supported; often restricted from modification and must be carefully documented
- **Dependencies** - Other systems or software components that a change may affect or require updates to before the primary change can be completed
- **Version Control** - A method of tracking changes to configurations, code, or OS versions over time

### Notes
- Enterprise environments have many interconnected components; all must be accounted for before making any change
- The **scope** of a change is defined by the change control board; if the primary goal requires expanding scope, formal approval must be obtained first
- For 24/7 operations, a **secondary system** should be available during changes to maintain uptime and allow easy rollback if needed
- **Legacy applications** may have no vendor support and fragile dependencies; in many cases you will be asked to document rather than modify them
- **Dependencies** must be identified early; upgrading one system may require upgrading libraries, services, or other software it relies on
- All changes must be accompanied by updated **documentation** including diagrams, updated policies, and configuration records
- **Version control** tracks changes over time and applies to OS builds, router configurations, and application code; some systems have it built in, others rely on third-party tools

---

## 1.4 Cryptographic Solutions

---

### Public Key Infrastructure
**Video length: 9:08**

### Key Concepts
- **Public Key Infrastructure (PKI)** - The full set of policies, procedures, hardware, software, and roles involved in creating, distributing, managing, storing, and revoking digital certificates
- **Symmetric Encryption** - Uses a single shared key for both encryption and decryption
- **Asymmetric Encryption** - Uses a mathematically linked key pair: a public key to encrypt and a private key to decrypt
- **Key Escrow** - A system where encryption keys are stored by a trusted third party or secured internal storage for recovery purposes

### Notes
- **Symmetric encryption** uses the same key to encrypt and decrypt; the key must be kept secret by all parties, does not scale well, but is very fast
- **Asymmetric encryption** uses two mathematically related keys:
    - Data encrypted with the **public key** can only be decrypted with the corresponding **private key**
    - Multiple senders can encrypt messages with the same public key, but only the private key holder can decrypt them
    - The **private key cannot be derived from the public key**
- Asymmetric key pairs are generated together using large prime numbers and randomization
- **Key escrow** is used in larger organizations to ensure keys can be recovered if the original holder loses access
- Handing off a private key is a significant security risk; third-party escrow providers must be highly trusted before being given this responsibility

---

### Encrypting Data
**Video length: 9:48**

### Key Concepts
- **Encryption at Rest** - Encrypting data stored on a disk, volume, or database
- **Encryption in Transit** - Encrypting data as it moves across a network
- **Transparent Encryption** - Encrypts an entire database using a symmetric key without requiring changes to the application
- **Record-level Encryption** - Encrypts specific columns within a database rather than the entire dataset
- **Key Stretching** - A technique that repeatedly hashes a key or password to make brute force attacks significantly harder

### Notes
- **Full disk encryption** protects all data on a drive; partition or volume encryption can be applied selectively
- In Windows: File > Properties > Advanced Attributes > Encrypt Contents
- **Transparent encryption** encrypts all database data using a single symmetric key; simpler to implement but less granular
- **Record-level encryption** targets only sensitive columns, for example encrypting only the SSN column in an employee table while leaving other fields readable
- **Encryption algorithms** are mathematical formulas applied by both parties; both sides must use the same algorithm; different algorithms offer different trade-offs between speed and security strength
- Well-known algorithms are generally more trustworthy because they have been publicly reviewed; the security depends on keeping the key secret, not the algorithm secret
- **Key length** must be long enough to prevent brute force: 128-bit is the standard minimum for symmetric encryption; asymmetric keys are commonly 2048 bits or longer due to the mathematical complexity involved
- **Key stretching** hashes a password, then hashes the result repeatedly to produce a much harder-to-crack final key

---

### Key Exchange
**Video length: 3:39**

### Key Concepts
- **Key Exchange** - The process of securely sharing an encryption key with another party
- **Out-of-Band Key Exchange** - Sharing a key through a separate channel such as phone, courier, or in person
- **In-Band Key Exchange** - Sharing a key over the network, typically by encrypting it using asymmetric encryption
- **Key Exchange Algorithm** - A mathematical method that allows two parties to independently derive the same symmetric key without ever transmitting it directly

### Notes
- The core problem in cryptography is keeping keys private: symmetric encryption requires both parties to securely share one key; asymmetric encryption requires protecting the private key
- In a **key exchange algorithm** such as Diffie-Hellman, Party A combines their private key with Party B's public key, and Party B combines their private key with Party A's public key; both operations produce the same shared symmetric key without the key ever being sent across the network

---

### Encryption Technologies
**Video length: 6:53**

### Key Concepts
- **Trusted Platform Module (TPM)** - A dedicated chip built into a device's motherboard that provides hardware-based cryptographic functions
- **Hardware Security Module (HSM)** - An enterprise-grade dedicated hardware device used to generate, store, and manage cryptographic keys at scale

### Notes
- **TPM** functions include:
    - Random number generation and key generation
    - Persistent memory with keys burned in during manufacturing
    - Versatile memory for creating and storing additional keys, protected by a password
- **HSM** is designed for enterprise environments and offers:
    - Similar functions to a TPM but at much greater scale
    - High redundancy, often deployed in clusters
    - Dedicated CPUs that act as cryptographic accelerators for high-volume operations
- **Key management systems** can be deployed locally or in the cloud and keep keys separate from the data they protect; they assign keys to users, maintain key logs, and handle key rotation
- **Secure enclaves** are isolated processing environments built into a chip with their own boot ROM; they handle real-time memory encryption and store cryptographic keys separate from the main OS

---

### Obfuscation
**Video length: 8:00**

### Key Concepts
- **Obfuscation** - Making data difficult to understand or interpret; can be reversible if the original process is known
- **Steganography** - Hiding information within another file such as an image, audio file, or video without visibly altering it
- **Tokenization** - Replacing sensitive data with a non-sensitive placeholder called a token; the original data is stored securely and retrieved by exchanging the token with an authorized server
- **Data Masking** - Hiding portions of sensitive data for display purposes, such as showing only the last four digits of a credit card number

### Notes
- Common **steganography** techniques include:
    - Embedding hidden messages within TCP packet headers
    - Invisible yellow dot patterns printed by many laser printers that encode the printer's serial number and timestamp (a real tracking mechanism used by governments)
    - Hiding data within audio files by altering least-significant bits
- In **tokenization**, a value like a Social Security Number is replaced with a random token; the token is used throughout a system, and only an authorized server can resolve it back to the original value; the original data never needs to be exposed during normal operations

---

### Hashing and Digital Signatures
**Video length: 10:24**

### Key Concepts
- **Hash** - A fixed-length string produced by running data through a hashing algorithm; it cannot be reversed to recover the original data and is used to verify integrity
- **Salt** - Random data added to input before hashing to ensure identical inputs produce different hashes, preventing precomputed attack tables
- **Digital Signature** - Proves integrity, source, and non-repudiation by combining a document's hash with the sender's private key

### Notes
- Any change to input data, even a single character, produces a completely different hash; this makes hashes reliable for detecting tampering
- Common uses of hashing: file integrity verification and password storage
- **Salting** solves the problem of identical passwords producing identical hashes; even if two users have the same password, their salted hashes will differ, making precomputed rainbow table attacks ineffective
- A **digital signature** is created by hashing a document and encrypting that hash with the sender's private key; the receiver decrypts the hash with the sender's public key and compares it to their own hash of the document to verify both identity and integrity

---

### Blockchain Technology
**Video length: 2:22**

### Key Concepts
- **Blockchain** - A distributed, decentralized ledger that records transactions across a network and stores copies on multiple systems simultaneously

### Notes
- How a blockchain works:
    - Transactions are grouped into **blocks**, each containing its own data and a hash of its contents
    - Each block also contains the hash of the previous block, creating a chain; altering any block breaks all subsequent links
    - No single point of control; at least 51% of nodes on the network must agree before a new block is added
- Key properties:
    - **Immutability** - Once written, a block cannot be changed or deleted
    - **Integrity and Non-Repudiation** - Transactions are digitally signed and cannot be altered after the fact
    - **Transparency** - The ledger is publicly viewable by anyone on the network
- Security use cases:
    - **Supply chain security** - Tracking hardware from manufacturer to deployment to detect counterfeits
    - **Digital identity** - Tamper-proof identity verification systems
    - **Audit trails** - Storing logs on a blockchain makes it impossible for attackers to alter or erase evidence

---

### Certificates
**Video length: 14:38**

### Key Concepts
- **Digital Certificate** - An electronic document that binds a public key to an identity; used to establish trust between parties
- **Root of Trust** - An inherently trusted component (hardware, software, or firmware) that serves as the foundation for a chain of trust
- **Certificate Authority (CA)** - A trusted third party that digitally signs certificates, vouching for the identity of the certificate holder
- **Certificate Signing Request (CSR)** - A formal request submitted to a CA to obtain a signed certificate
- **Wildcard Certificate** - A certificate that applies to a domain and all of its subdomains

### Notes
- Certificates enable a **chain of trust**: if we trust the CA, and the CA has verified and signed a certificate, we can trust the entity presenting that certificate
- The **X.509** certificate standard contains: serial number, version, signature algorithm, issuer, certificate holder name, public key, validity dates, and extensions
- The browser trust model works as follows: the user trusts the browser, the browser trusts a set of known CAs, those CAs sign website certificates, so the user can trust those websites
- The **CA validation step** during a CSR is the most critical part of the process; it verifies the identity of whoever is requesting the certificate
- Medium to large organizations often operate an **internal CA** to issue certificates for internal devices and services
- **Wildcard certificates** are issued for a domain (e.g. *.example.com) and are valid for any subdomain under that domain, reducing the need to issue individual certificates per server

---

## Section 1 — Vocab & Acronyms
| Term | Definition |
|------|------------|
| **CIA Triad** | Confidentiality, Integrity, Availability; the three foundational goals of IT security |
| **Non-Repudiation** | Proof that a message was sent by a specific sender and was not altered in transit |
| **Hash** | A fixed-length string representing specific data, used to verify integrity |
| **Salt** | Random data added to input before hashing to prevent identical inputs from producing identical hashes |
| **Private Key** | An encryption key known only to its owner |
| **Public Key** | An encryption key shared openly with other parties |
| **Digital Signature** | A hash of a message encrypted with a private key, used to verify identity and integrity |
| **CA (Certificate Authority)** | A trusted entity that issues and signs digital certificates |
| **CSR (Certificate Signing Request)** | A request submitted to a CA to obtain a signed certificate |
| **PKI (Public Key Infrastructure)** | The full system of policies, hardware, software, and procedures for managing digital certificates and keys |
| **Symmetric Encryption** | Encryption using a single shared key for both encryption and decryption |
| **Asymmetric Encryption** | Encryption using a public/private key pair; public encrypts, private decrypts |
| **Key Escrow** | Secure storage of encryption keys by a trusted third party for recovery purposes |
| **TPM (Trusted Platform Module)** | A chip on a motherboard providing hardware-based cryptographic functions |
| **HSM (Hardware Security Module)** | Enterprise hardware device for generating, storing, and managing keys at scale |
| **Tokenization** | Replacing sensitive data with a non-sensitive token that maps back to the original via a secure server |
| **Steganography** | Hiding data within another file such as an image or audio file |
| **Key Stretching** | Repeatedly hashing a key or password to make brute force attacks harder |
| **PEP (Policy Enforcement Point)** | Gatekeeper on the data plane that controls which traffic is allowed through |
| **PDP (Policy Decision Point)** | Control plane component that evaluates policy and decides to grant or deny access |
| **Zero Trust** | Security model where no user or device is trusted by default; all access must be verified |
| **Honeypot** | A decoy system used to attract attackers and observe their methods |
| **Gap Analysis** | A comparison of current security posture against a target baseline to identify shortfalls |
| **NIST 800-171** | Framework for protecting controlled unclassified information in federal systems |
| **ISO/IEC 27001** | International standard for information security management systems |
| **Wildcard Certificate** | A certificate valid for a domain and all of its subdomains |
| **Blockchain** | A distributed, decentralized ledger that records tamper-proof transactions across a network |

---

## Section 1 — Practice Exam Weak Areas
-
