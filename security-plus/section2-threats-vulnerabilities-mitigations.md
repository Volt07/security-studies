# Section 2 — Threats, Vulnerabilities, and Mitigations

**Exam weight: 22%**

---

## 2.1 Threat Actors

**Video length: 10:23**

### Key Concepts

**Summary:** Threat actors are classified by origin, resources, sophistication, and motivation. Classification determines the defensive posture required.

- **Threat Actor** — The individual or group responsible for carrying out a malicious attack.

### Notes

- A threat actor may be external or internal to an organization; sophistication varies widely by actor type.
- Common motivations: information theft, disruption, financial gain, ideology, espionage, war.

| Threat Actor | Location | Resources | Sophistication | Possible Motivations |
|---|---|---|---|---|
| Nation State | External | Extensive | Very high | Data exfiltration, ideology, revenge, disruption, war |
| Unskilled Attacker | External | Limited | Very low | Disruption, data exfiltration, ideology |
| Hacktivist | External | Some funding | Can be high | Ideology, revenge, disruption/chaos |
| Insider Threat | Internal | Many resources | Medium | Revenge, financial gain |
| Organized Crime | External | Often extensive | Very high | Financial gain |
| Shadow IT | Internal | Many resources | Limited | Convenience, ideology, revenge |

---

## 2.2 Threat Vectors and Attack Surfaces

### Common Threat Vectors

**Video length: 17:14**

### Key Concepts

**Summary:** A threat vector is the path an attacker uses to reach a target. Vectors span message, image, file, voice, physical, network, and supply-chain channels.

- **Threat Vector** — The method an attacker uses to gain entry or access to information, resources, or a location.
- **Attack Surface** — The total set of points where an attacker could attempt entry.

### Notes

- **Message-based vectors** — Email phishing links and malware, SMS phishing links. Phishing uses social engineering to obtain information or money; malware can also be embedded in websites via injected scripts.
- **Image-based vectors** — The SVG format embeds an XML file, which can carry injected JavaScript or other payloads.
- **File-based vectors** — Executables are the most obvious carrier, but PDFs support scripting, ZIP/RAR archives may contain hidden threats, and Microsoft Office files can run malicious macros.
- **Voice vectors** — Vishing (voice phishing) via phone calls, AI-based voice cloning, and SPIT (Spam over Internet Telephony), which enables large-scale automated calling campaigns.
- **Removable device vectors** — USB drives can carry malware or emulate a keyboard (HID attack) to run scripts or macros automatically on connection.
- **Unsupported / End-of-Life (EOL) vectors** — Software past its support date receives no further security patches; any newly discovered vulnerability becomes a permanent, unpatched entry point.
- **Unsecure network vectors** — Wireless networks must enforce strong encryption (e.g., WPA3) and proper authentication to prevent interception or unauthorized access.
- **Open service ports** — Every network service uses a TCP/UDP port; each open port is a potential attack surface. Every new application adds a new open port. Inbound/outbound firewall rules significantly reduce exposure.
- **Default credentials** — Default usernames and passwords (e.g., admin/admin on routers) must always be changed before deployment.
- **Supply chain vectors** — Malware can be introduced during manufacturing or transit (e.g., compromised firmware installed on a switch before delivery).

---

### Phishing

**Video length: 6:32**

### Key Concepts

**Summary:** Phishing is social engineering delivered through digital communication channels, often paired with spoofing and a fabricated pretext to increase credibility.

- **Phishing** — Social engineering combined with spoofing, delivered via email, text message, or other communication channels.
- **Pretexting** — A fabricated story or scenario used to make a phishing attack more believable.
- **Typosquatting** — Registering domains with common misspellings of legitimate sites (e.g., `go0gle.com`) to capture users who mistype a URL.

### Notes

- Most commonly delivered via email and SMS, typically containing malicious links or attachments.
- Variants include spear phishing (targeted at a specific individual) and whaling (targeted at executives).

---

### Impersonation

**Video length: 5:52**

### Key Concepts

**Summary:** Impersonation is a pretexting technique where the attacker poses as a trusted person or authority to extract sensitive information, often leading to identity fraud.

- **Impersonation** — A form of pretexting in which an attacker poses as a trusted individual or authority figure.
- **Identity Fraud** — The use of stolen personal information to act as the victim, such as opening accounts or committing loan fraud.

### Notes

- The goal is typically to extract information the attacker would not otherwise have access to (e.g., SSN, banking details, credit information).
- Identity fraud can result in an attacker opening a credit card or bank account in the victim's name, or committing loan fraud.
- Best defenses: never share personal information unsolicited; always independently verify a caller's or sender's identity through a separate, trusted channel.

---

### Watering Hole Attacks

**Video length: 4:12**

### Key Concepts

**Summary:** Rather than attacking a well-defended target directly, the attacker compromises a third-party site the target is known to trust and visit.

- **Watering Hole Attack** — An attack in which the adversary compromises a third-party site or service the target frequently visits, rather than attacking the target directly.

### Notes

- The attacker identifies and compromises a site the target regularly accesses, then waits for the target to visit and become infected.
- Mitigation requires **defense in depth** — multiple overlapping layers of security so that no single point of failure grants full access.

---

### Other Social Engineering Attacks

**Video length: 3:29**

### Key Concepts

**Summary:** Beyond phishing and impersonation, attackers exploit trust in information and brands to manipulate targets at scale.

- **Misinformation** — False or inaccurate information spread without intent to deceive.
- **Disinformation** — Deliberately fabricated or misleading information used to persuade, distract, or create conflict.
- **Brand Impersonation** — Use of a company's name or logo to make users believe the brand said or did something it did not.

### Notes

- Brand impersonation leverages existing trust in a company to spread false narratives or collect credentials through fake login pages, emails, or social media accounts.

---

## 2.3 Types of Vulnerabilities

### Memory Injections

**Video length: 2:39**

### Key Concepts

**Summary:** Memory injection attacks run malicious code within the memory space of legitimate processes, making detection difficult and giving the malware the host process's privilege level.

- **Memory Injection** — Malware that runs at the memory level, either as its own process or injected into another running process.
- **DLL Injection** — A technique where an attacker forces a legitimate process to load and execute a malicious Dynamic Link Library (DLL).

### Notes

- Injecting into another process makes malware easier to hide and allows it to inherit that process's privileges.
- A DLL is a Windows library of shared code and data that multiple applications can use. Attackers inject a path to a malicious DLL so it executes as part of a trusted process.

---

### Buffer Overflows

**Video length: 3:37**

### Key Concepts

**Summary:** A buffer overflow occurs when a program writes more data to a memory buffer than it was allocated to hold, allowing an attacker to corrupt adjacent memory and potentially execute arbitrary code.

- **Buffer Overflow** — An attack in which a program writes more data into a fixed-size memory buffer than it can hold, overwriting adjacent memory.

### Notes

- The attacker's goal is to find a repeatable, functional exploit that provides an advantage, such as crashing the application (denial of service) or hijacking execution flow to run injected code.
- **Example:** A login form allocates a 100-character buffer for a username. If the application does not enforce that limit and a user submits 500 characters, the extra 400 characters overwrite adjacent memory, including the return address on the stack. A crafted overflow can overwrite that return address to point to attacker-supplied code, causing the program to execute it with the same privileges as the vulnerable application. This class of attack is mitigated by input length validation, bounds checking, stack canaries, and Address Space Layout Randomization (ASLR).

---

### Race Conditions

**Video length: 4:58**

### Key Concepts

**Summary:** A race condition occurs when the outcome of a process depends on the timing of uncontrolled events, allowing an attacker to exploit the gap between a check and its corresponding action.

- **Race Condition** — A vulnerability where two or more operations occur concurrently, and the timing or order of execution produces an unintended outcome.
- **TOCTOU (Time-of-Check to Time-of-Use)** — A specific race condition where a system checks a resource's state, then acts on it, but the state changes in between.

### Notes

- In a TOCTOU attack, the system checks a condition (e.g., file permissions), then uses the resulting value — but the underlying resource can change between the check and the use, invalidating the assumption.
- **Example:** NASA's Spirit rover experienced a flash-memory file system fault in January 2004 that caused a continuous reboot cycle; the corrupted file system caused reboots, and each reboot attempt failed to complete the process needed to fix it, until engineers intervened remotely.

---

### Malicious Updates

**Video length: 5:45**

### Key Concepts

**Summary:** Software updates are a trusted delivery channel, which makes them a high-value target; an attacker who compromises the update process can distribute malware to every user of that software.

- **Malicious Update** — A software update that has been tampered with, either at the source or in transit, to deliver malicious code instead of, or in addition to, the intended fix.

### Notes

- Verify that an update is legitimate: confirm the developer is trusted, obtain updates directly from the vendor's official site, and check digital signatures.
- Back up system state before applying any update.
- Auto-updating applications typically perform their own integrity checks, but this is not a guarantee of safety.
- If an attacker compromises a developer's build or distribution pipeline, malicious code can be inserted and distributed to all users through the normal, trusted update mechanism (a supply chain attack).

---

### Operating System Vulnerabilities

**Video length: 4:09**

### Key Concepts

**Summary:** Operating systems are large, complex codebases, which makes them a persistent source of discovered vulnerabilities; timely patching and pre-deployment testing are the primary mitigations.

- **OS Vulnerability** — A flaw in an operating system's code that can be exploited to gain unauthorized access or control.

### Notes

- Operating systems are extremely complex; Windows alone contains on the order of tens of millions of lines of code.
- Microsoft releases security patches on a monthly cadence ("Patch Tuesday") to address newly discovered vulnerabilities.
- Always plan to update as soon as practical, maintain backups before updating, and test patches in a non-production environment before full deployment.

---

### SQL Injection

**Video length: 5:09**

### Key Concepts

**Summary:** SQL injection exploits improperly sanitized user input to insert attacker-controlled commands into a database query, potentially exposing or modifying data the application was never meant to expose.

- **SQL Injection** — An attack that inserts attacker-controlled input into a database query, altering its intended logic.

### Notes

- **Example:** An application builds a query by directly concatenating user input: `SELECT * FROM users WHERE name = '" + userName + "'`. If `userName` is not sanitized, an attacker can submit a value like `' OR '1'='1` to make the WHERE clause always true, returning every row in the table.
- This class of vulnerability is most common in web applications that fail to sanitize or parameterize user input.
- Mitigations: parameterized queries (prepared statements), input validation, and least-privilege database accounts.

---

### Cross-Site Scripting (XSS)

**Video length: 8:34**

### Key Concepts

**Summary:** Cross-site scripting injects attacker-controlled script into a trusted website, which then executes in the browser of anyone who views the affected page.

- **Cross-Site Scripting (XSS)** — An attack in which malicious script, typically JavaScript, is injected into a trusted website and executed in a victim's browser.

### Notes

- **Non-persistent (reflected) XSS** — The malicious script is reflected off a website's input handling (e.g., a search box) and executes only for the user who submits the crafted input.
- **Persistent (stored) XSS** — The attacker's script is stored on the target server (e.g., in a social media post or comment) and executes for every user who views the affected content.
- User-side mitigations: avoid clicking untrusted third-party links, disable or restrict JavaScript where practical, keep browsers updated.
- Developer-side mitigations: sanitize and encode all user input before rendering it, and apply a strict Content Security Policy.

---

### Hardware Vulnerabilities

**Video length: 6:27**

### Key Concepts

**Summary:** Hardware carries its own security lifecycle, distinct from software; firmware and legacy platforms create risk when vendors stop issuing updates.

- **Firmware** — Low-level software embedded in hardware; updates are typically controlled and distributed by the hardware vendor.
- **End of Life (EOL)** — The point at which a vendor stops selling a product; security patches may continue for a defined period afterward.
- **End of Service Life (EOSL)** — The point at which a vendor stops selling a product and stops issuing security patches; continued use carries unpatched risk.
- **Legacy Platform** — A system that has been in use for an extended period; continued use requires weighing the cost of replacement against the growing risk of unpatched vulnerabilities.

### Notes

- IoT devices commonly run embedded operating systems the owner has no direct control over, while still connecting to the network — creating persistent, hard-to-mitigate risk.

---

### Virtualization Vulnerabilities

**Video length: 5:29**

### Key Concepts

**Summary:** Virtualized environments introduce risks specific to shared infrastructure, including the possibility of breaking isolation between virtual machines.

- **VM Escape** — A rare but severe vulnerability where an attacker breaks out of an isolated virtual machine and gains access to the hypervisor or other VMs on the same host.
- **Resource Reuse** — The risk that physical resources (memory, storage) shared across VMs are not fully cleared between uses, potentially exposing one tenant's data to another.

### Notes

- Cloud environments can host many VMs with differing configurations, making consistent security management difficult.
- Risks include local privilege escalation, command injection, and information disclosure.
- VMs are designed to be isolated from one another, but a VM escape — though rare — allows an attacker to move between VMs on the same hypervisor.
- **Example:** A hypervisor with 4 GB of RAM hosting three VMs each allocated 2 GB relies on memory being properly isolated and cleared between allocations; improper isolation could allow data to leak between VMs.

---

### Cloud-Specific Vulnerabilities

**Video length: 4:06**

### Key Concepts

**Summary:** Cloud platforms centralize sensitive data and expose it through internet-facing applications and APIs, making misconfiguration and weak authentication especially costly.

- **Cloud Vulnerability** — A weakness specific to cloud infrastructure, often stemming from misconfiguration, weak authentication, or insecure application code.

### Notes

- Sensitive data is frequently stored in the cloud, increasing the impact of any breach.
- Industry research has repeatedly found a large share of cloud codebases contain insecure code, and that a significant portion of organizations do not enforce multi-factor authentication (MFA) on critical cloud resources. Exact figures vary by source and year; verify current statistics before citing them in an exam or report context.
- Risks include DDoS attacks, authentication bypass, and misconfigurations that enable directory traversal.
- Poorly configured or vulnerable applications can be exploited to gain access to underlying cloud functions.
- Out-of-bounds write vulnerabilities allow writes to unauthorized memory areas, causing data corruption, crashes, or enabling further exploitation such as SQL injection.

---

### Supply Chain Vulnerabilities

**Video length: 9:12**

### Key Concepts

**Summary:** A supply chain has many participants and handoff points, and a compromise at any single step can propagate to every downstream customer.

- **Supply Chain Vulnerability** — A weakness introduced at any stage of a product or service's supply chain — manufacturing, distribution, or service delivery.

### Notes

- Service providers (cleaning, electrical, plumbing, HVAC, IT contractors) are responsible for their own security; the client organization is trusting the provider's practices by extension.
- Ongoing security audits can be written into service contracts to verify a provider maintains current security practices.
- Hardware providers: organizations must decide how much to trust new hardware and vendors, and should apply zero-trust principles when integrating new hardware.
- Software providers: organizations must evaluate the trustworthiness of software vendors and the integrity of their update mechanisms.

---

### Misconfiguration Vulnerabilities

**Video length: 7:09**

### Key Concepts

**Summary:** Misconfigurations are unintentional security gaps left by default settings, weak credentials, or unencrypted protocols — among the most common and most preventable vulnerability classes.

- **Open Permission** — A misconfiguration where access controls are left too permissive, unintentionally exposing data or systems.

### Notes

- Root/admin accounts must not use default credentials; passwords must not be easily guessable; the number of admin accounts should be limited; direct admin login should be disabled where possible in favor of privilege escalation from a standard account.
- Insecure protocols such as FTP, SMTP, Telnet, and IMAP transmit traffic unencrypted. Use encrypted equivalents instead: SFTP, SMTPS, SSH, IMAPS. Unencrypted traffic is trivially readable via packet capture.
- Default settings and default logins are frequently left unchanged after deployment, creating an easy entry point.
- Every new service opens a new port; manage exposure with a firewall, restricting by port number or application as needed.

---

### Mobile Device Vulnerabilities

**Video length: 3:23**

### Key Concepts

**Summary:** Mobile devices carry sensitive data, operate outside traditional network perimeters, and are frequently in motion — all of which require security policies distinct from those for fixed infrastructure.

- **Rooting** — Bypassing built-in restrictions on an Android device to obtain full administrative control over the OS.
- **Jailbreaking** — Bypassing built-in restrictions on an iOS device to obtain full administrative control over the OS.
- **Sideloading** — Installing an application from a source other than the official app store.

### Notes

- Mobile operating systems are normally locked down, restricting user access to the underlying OS; rooting and jailbreaking bypass these restrictions, removing built-in security protections in the process.
- Risks include poorly written app code and a lack of restrictions on what can be installed.
- Sideloading bypasses app store vetting, increasing exposure to malicious or poorly secured applications.

---

### Zero-Day Vulnerabilities

**Video length: 3:02**

### Key Concepts

**Summary:** A zero-day vulnerability is unknown to the vendor at the time it is exploited, meaning no patch exists and defenders have zero days of advance warning.

- **Zero-Day Vulnerability** — A previously unknown vulnerability, exploited before the vendor is aware of it or has issued a patch.

### Notes

- These attacks are especially dangerous because no patch or established mitigation exists at the time of exploitation.
- Once discovered, it becomes a race between attackers exploiting the flaw further and vendors developing and distributing a patch.

---

## 2.4 Indicators of Malicious Activity

---

### An Overview of Malware

**Video length: 6:06**

### Key Concepts

-

### Notes

-

---

### Viruses and Worms

**Video length: 5:54**

### Key Concepts

-

### Notes

-

---

### Spyware and Bloatware

**Video length: 4:21**

### Key Concepts

-

### Notes

-

---

### Other Malware Types

**Video length: 7:32**

### Key Concepts

-

### Notes

-

---

### Physical Attacks

**Video length: 4:04**

### Key Concepts

-

### Notes

-

---

### Denial of Service

**Video length: 6:07**

### Key Concepts

-

### Notes

-

---

### DNS Attacks

**Video length: 8:57**

### Key Concepts

-

### Notes

-

---

### Wireless Attacks

**Video length: 7:55**

### Key Concepts

-

### Notes

-

---

### On-path Attacks

**Video length: 5:30**

### Key Concepts

-

### Notes

-

---

### Replay Attacks

**Video length: 5:45**

### Key Concepts

-

### Notes

-

---

### Malicious Code

**Video length: 3:40**

### Key Concepts

-

### Notes

-

---

### Application Attacks

**Video length: 11:48**

### Key Concepts

-

### Notes

-

---

### Cryptographic Attacks

**Video length: 9:31**

### Key Concepts

-

### Notes

-

---

### Password Attacks

**Video length: 7:15**

### Key Concepts

-

### Notes

-

---

### Indicators of Compromise

**Video length: 10:59**

### Key Concepts

-

### Notes

-

---

## 2.5 Mitigation Techniques

---

### Segmentation and Access Control

**Video length: 6:06**

### Key Concepts

-

### Notes

-

---

### Mitigation Techniques

**Video length: 6:51**

### Key Concepts

-

### Notes

-

---

### Hardening Techniques

**Video length: 12:11**

### Key Concepts

-

### Notes

-

---

## Section 2 — Vocab & Acronyms

| Term | Definition |
|------|------------|
| | |

---

## Section 2 — Practice Exam Weak Areas

-
