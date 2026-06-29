# Section 2 — Threats, Vulnerabilities, and Mitigations

**Exam weight: 22%**

---

## 2.1 Threat Actors

**Video length: 10:23**

### Key Concepts

- **Threat Actor** — The cause of an event; the malicious actor responsible for carrying out an attack

### Notes

- A threat actor could be external or internal to a company; sophistication varies widely
- Motivations include: information theft, disruption, financial gain, and ideology

| Threat Actor | Location | Resources | Sophistication | Possible Motivations |
|---|---|---|---|---|
| Nation State | External | Extensive | Very high | Data exfiltration, philosophical, revenge, disruption, war |
| Unskilled Attacker | External | Limited | Very low | Disruption, data exfiltration, philosophical beliefs |
| Hacktivist | External | Some funding | Can be high | Philosophical beliefs, revenge, disruption/chaos |
| Insider Threat | Internal | Many resources | Medium | Revenge, financial gain |
| Organized Crime | External | Often extensive | Very high | Financial gain |
| Shadow IT | Internal | Many resources | Limited | Philosophical beliefs, revenge |

---

## 2.2 Threat Vectors and Attack Surfaces

---

### Common Threat Vectors

**Video length: 17:14**

### Key Concepts

- **Threat Vector** — The method an attacker uses to gain entry or access to information, resources, or a location

### Notes

- **Message-based vectors** — Email phishing links and malware, SMS links; phishing uses social engineering to gain info or money; malware can be embedded in websites via injected scripts
- **Image-based vectors** — SVG format contains an embedded XML file, which can carry injected JavaScript or other payloads
- **File-based vectors** — Executables are the most obvious, but PDFs support scripting, ZIP/RAR archives may contain threats, and Microsoft Office files can run macros
- **Voice vectors** — Vishing via phone calls, AI-powered voice cloning, and SPIT (Spam over IP Telephony) enables large-scale attack campaigns
- **Removable device vectors** — USB drives can carry malware or emulate a keyboard (HID attack) to run scripts or macros automatically
- **Unsupported/End-of-Life (EOL) vectors** — Software past its support date receives no security patches; any discovered vulnerability becomes a permanent open door
- **Unsecure network vectors** — Wireless networks must enforce security protocols and proper authentication
- **Open service ports** — Every network service uses a TCP/UDP port; each open port is an attack surface; every new application adds a new open port; inbound/outbound firewall rules significantly reduce exposure
- **Default credentials** — Default usernames and passwords (e.g., admin/password on routers) must always be changed
- **Supply chain vectors** — Malware can be introduced during manufacturing or transit (e.g., compromised firmware on a switch before delivery)

---

### Phishing

**Video length: 6:32**

### Key Concepts

- **Phishing** — Social engineering combined with spoofing, delivered via email, text, or other communication channels
- **Pretexting** — A fabricated story used to make a phishing attack more believable

### Notes

- Most commonly delivered via email and SMS, typically using malicious links
- **Typosquatting** — Registering domains with common misspellings (e.g., `go0gle.com/login`) to capture users who mistype a URL

---

### Impersonation

**Video length: 5:52**

### Key Concepts

- **Impersonation** — A form of pretexting where an attacker poses as a trusted individual or authority figure

### Notes

- Goal is typically to extract information the attacker wouldn't otherwise have access to (e.g., SSN, banking details, credit info)
- **Identity fraud** — A major outcome of impersonation; an attacker posing as you can:
  - Open a credit card or bank account in your name
  - Commit loan fraud
- Best defenses: never share personal information unsolicited; always independently verify a caller's or sender's identity

---

### Watering Hole Attacks

**Video length: 4:12**

### Key Concepts

- **Watering Hole Attack** — Instead of attacking the primary target directly, the attacker compromises a third-party site or service the target is known to visit

### Notes

- Attacker compromises a third-party site they know the target frequently accesses, then waits for the target to visit
- Mitigation requires **defense in depth** — multiple overlapping layers of security so that no single failure provides full access

---

### Other Social Engineering Attacks

**Video length: 3:29**

### Key Concepts

- **Misinformation** — False or inaccurate information spread unintentionally
- **Disinformation** — Deliberately fabricated or misleading information used to persuade, distract, or create conflict

### Notes

- Brand impersonation — Attackers use a company's name or logo to make users believe the brand said or did something it didn't, leveraging trust to spread false narratives or collect credentials

---

## 2.3 Types of Vulnerabilities

---

### Memory Injections

**Video length: 2:39**

### Key Concepts

-

### Notes

-

---

### Buffer Overflows

**Video length: 3:37**

### Key Concepts

-

### Notes

-

---

### Race Conditions

**Video length: 4:58**

### Key Concepts

-

### Notes

-

---

### Malicious Updates

**Video length: 5:45**

### Key Concepts

-

### Notes

-

---

### Operating System Vulnerabilities

**Video length: 4:09**

### Key Concepts

-

### Notes

-

---

### SQL Injection

**Video length: 5:09**

### Key Concepts

-

### Notes

-

---

### Cross-site Scripting

**Video length: 8:34**

### Key Concepts

-

### Notes

-

---

### Hardware Vulnerabilities

**Video length: 6:27**

### Key Concepts

-

### Notes

-

---

### Virtualization Vulnerabilities

**Video length: 5:29**

### Key Concepts

-

### Notes

-

---

### Cloud-specific Vulnerabilities

**Video length: 4:06**

### Key Concepts

-

### Notes

-

---

### Supply Chain Vulnerabilities

**Video length: 9:12**

### Key Concepts

-

### Notes

-

---

### Misconfiguration Vulnerabilities

**Video length: 7:09**

### Key Concepts

-

### Notes

-

---

### Mobile Device Vulnerabilities

**Video length: 3:23**

### Key Concepts

-

### Notes

-

---

### Zero-day Vulnerabilities

**Video length: 3:02**

### Key Concepts

-

### Notes

-

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
