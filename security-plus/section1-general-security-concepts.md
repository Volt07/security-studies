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
    - **Preventative** - Works *before* to avoid anything happening from step 1 by limiting access
    - **Deterrent** - Works *before* to cause apprehension towards malicious behavior
    - **Detective** - Works *during* to find any current exploits or attack attempts
    - **Corrective** - Works *after* to fix mistakes, reverse impact of attacks, reduce downtime
    - **Directive** - Works *in present/future* to inform and prevent through teaching information

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
- **Confidentiality** - Make sure only those who should access material can access it (Access Controls, Encryption, Authentication)
- **Integrity** - Information stays intact when sending/receiving (Hashing, Signatures, Certificates, Non-Repudiation and Proof of Identity)
- **Availability** - System must always be up and running so those who need to can access it (Redundancy, Fault Tolerance, Patching)

### Notes
- One of the biggest points of cybersecurity is maintaining a good combination of all 3 elements of the **CIA Triad**, which ensures peak data security

---

### Non-Repudiation
**Video length: 7:57**

### Key Concepts
- **Non-Repudiation** - Ensures proof of sender and proof of integrity of the information sent
- **Hash** - A short string of characters used to represent exact data
- **Private Key** - Only known to the sender
- **Public Key** - Known to all
- **Digital Signature** - Created with hash of plaintext and private key, sent alongside the plaintext

### Notes
- Works as a signed contract — what you said is what you said
- Proof of integrity means Sent = Received
- A **hash** can be used to verify data integrity by comparing hashes before and after transmission
- Sending plaintext with a **digital signature** created with the sender's **private key** allows the receiver to use the **public key** to verify both integrity and identity via the hash

---

### Authentication, Authorization, and Accounting
**Video length: 9:03**

### Key Concepts
- **Identification** - Who you claim to be (username)
- **Authentication** - Proof you are who you claim to be (password)
- **Authorization** - Identification + Authentication = what areas do you have access to?
- **Accounting** - Log of in/out times, data sent/received
- **Certificate** - An electronic credential distributed by a **Certificate Authority (CA)** which verifies a device's identity

### Notes
- AAA Server network traffic example:
    - Client → Internet → Firewall → (Authenticate?) AAA Server → (Credentials Approved) → File Server
- You can authenticate a device using a **digital certificate**, commonly used on company devices
- A **Certificate Authority (CA)** distributes certificates — most companies maintain their own CA
- **Authorization models** (roles, organizations, permission lists) make scaling permissions for larger groups much easier
- **Abstractions** are a type of authorization model where roles/groups with permissions are assigned to groups of users, similar to a permission list

---

### Gap Analysis
**Video length: 6:44**

### Key Concepts
- **Gap** - The space between where your company is and where it should be (the goal)
- **Gap Framework (Baseline)** - Allows for a baseline standard for company security, could be a well-known standard or one dedicated to your company
- **Gap Analysis Report** - Final comparison providing a clear view of the current state of a company's gap, paired with a pathway forward and recommendations

### Notes
- Analysis requires long-term research of security posture
- Large gap frameworks:
    - **NIST Publication 800-171** - Protecting information in federal systems
    - **ISO/IEC 27001** - Information security management systems
- Analysis is done by comparing and contrasting existing security policy and implementation against a baseline, moving from broad to specific
- A gap analysis report may contain graphs or visual aids to make information easier to digest for the client

---

### Zero Trust
**Video length: 10:04**

### Key Concepts
- **Zero Trust** - Authenticating per resource; everything may have security checks, trust nothing inherently
- **Planes of Operation** - Split networks into different planes, e.g. Data Plane, Control Plane
- **Data Plane** - Processes frames, packets, and network data; moves frames from one interface to another
- **Control Plane** - Manages actions of the data plane; defines policy and rules
- **Threat Scope Reduction** - Limit the number of entry points into a system or network
- **Security Zones** - Used to segment trusted and untrusted areas, allows for implicit trust groups
- **Policy Enforcement Point (PEP)** - Gatekeeper on the data plane; all traffic flows through it; gathers info about source, destination, and traffic type
- **Policy Decision Point (PDP)** - Split into two components in the control plane:
    - **Engine** - Examines authentication, determines if access is allowed based on policies, grants/denies/revokes
    - **Administrator** - Communicates with PEP, generates credentials, tells PEP to allow or disallow

### Notes
- Everything must be verified: MFA, system permissions, firewalls, monitoring, certificates
- Splitting network logic using planes introduces segmentation
- The **data plane** processes and moves frames using hardware, executing decisions made by the control plane
- The **control plane** makes decisions about how traffic should be handled, runs routing protocols, builds routing tables, and defines ACLs
- Controlling trust can be done through **adaptive identity** — considering source IP, relationship to org, type of connection, and anything else that identifies a user or device
- **Policy-driven access controls** combine identity with a set of rules
- **Security zones** can designate untrusted or trusted areas — think department groups, VLANs — used to deny access and create implicit trust

---

### Physical Security
**Video length: 8:17**

### Key Concepts
- **Physical Security** - Goals to prevent or deter unauthorized personnel from accessing physical locations

### Notes
- **Access control vestibules** — all doors may be locked with only one open at a time; access granted through cards, biometrics, or a human checkpoint
- **Fencing** builds a strong perimeter; obvious but robust; should consider preventing climbing
- **Video surveillance (CCTV)** can reduce personnel costs; can be paired with motion detection and object detection, all networked together
- **Security guards** provide physical protection; best deployed in pairs for checks and balances
- **ID badges** can identify individuals and integrate with electronic locks
- **Lighting** is often underestimated; well-lit angles prevent unauthorized entry
- **Sensors:**
    - **Infrared** - Motion detectors, pressure sensors
    - **Microwave** - Detection over larger areas
    - **Ultrasonic** - Crash detection using reflected sound waves

---

### Deception and Disruption
**Video length: 4:30**

### Key Concepts
- **Honeypots** - Decoy systems used to attract attackers, observe their behavior, and identify them

### Notes
- **Honeynets** are like honeypots but consist of multiple devices, designed to convincingly simulate real networks
- **Honey files** contain fake information used to bait attackers; more effective when paired with alerts triggered on access
- **Honey tokens** are traceable data embedded in files so that if stolen, the source of the leak can be identified (cookies, tracking pixels)

---

## 1.3 Change Management

---

### Change Management
**Video length: 11:22**

### Key Concepts
- **Change Management** - The process of planning and implementing changes from start to finish
- **Change** - Anything from upgrading software, hardware, applying a patch, or modifying a firewall configuration
- **Stakeholder** - Anyone who may be impacted by a change; may want input on timing or content of the change

### Notes
- A **change approval request form** is often required for larger changes and should include:
    - The purpose of the change
    - The scope, date, and time of the change
    - Systems impacted and risk associated with the change, as well as risk associated with not making the change
    - Approval from the change control board
- **Impact analysis** must be conducted to assess risk value, considering that a fix may break something else
- Testing should be done in a **sandbox environment** (e.g. a VM) before deploying to production
- A strong **back-up plan** should always be in place, typically including backups of affected systems
- A **maintenance window** should be scheduled outside of business hours to avoid disruption, taking date, time, and holidays into consideration
- Change management should be part of a **standard operating document** to ensure consistent and smooth changes

---

### Technical Change Management
**Video length: 10:54**

### Key Concepts
-

### Notes
-

---

## 1.4 Cryptographic Solutions

---

### Public Key Infrastructure
**Video length: 9:08**

### Key Concepts
-

### Notes
-

---

### Encrypting Data
**Video length: 9:48**

### Key Concepts
-

### Notes
-

---

### Key Exchange
**Video length: 3:39**

### Key Concepts
-

### Notes
-

---

### Encryption Technologies
**Video length: 6:53**

### Key Concepts
-

### Notes
-

---

### Obfuscation
**Video length: 8:00**

### Key Concepts
-

### Notes
-

---

### Hashing and Digital Signatures
**Video length: 10:24**

### Key Concepts
-

### Notes
-

---

### Blockchain Technology
**Video length: 2:22**

### Key Concepts
-

### Notes
-

---

### Certificates
**Video length: 14:38**

### Key Concepts
-

### Notes
-

---

## Section 1 — Vocab & Acronyms
| Term | Definition |
|------|------------|
| **CIA Triad** | Confidentiality, Integrity, Availability — the foundational goals of IT security |
| **Non-Repudiation** | Proof that a message was sent by a specific sender and was not altered |
| **Hash** | A short fixed-length string representing exact data, used to verify integrity |
| **Private Key** | Encryption key known only to the sender |
| **Public Key** | Encryption key known to all parties |
| **Digital Signature** | Hash of plaintext encrypted with a private key, used to verify identity and integrity |
| **CA (Certificate Authority)** | Entity that distributes digital certificates to verify device identity |
| **PEP (Policy Enforcement Point)** | Gatekeeper on the data plane that controls traffic flow |
| **PDP (Policy Decision Point)** | Control plane component that decides whether to grant or deny access |
| **Zero Trust** | Security model where nothing is trusted inherently; everything requires verification |
| **Honeypot** | Decoy system used to attract and observe attackers |
| **Gap Analysis** | Comparison of current security posture against a target baseline |
| **NIST 800-171** | Framework for protecting information in federal systems |
| **ISO/IEC 27001** | International standard for information security management systems |

---

## Section 1 — Practice Exam Weak Areas
-
