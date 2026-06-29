aa# Section 2 — Threats, Vulnerabilities, and Mitigations
**Exam weight: 22%**

---

## 2.1 Threat Actors
**Video length: 10:23**

### Key Concepts
- Threat Actor - The cause of an event, the malicious actor

### Notes
- A threat actor could be external, but also internal at a company, some are more sophisiticated than others
- Motivation could be information, disruption, money, ideology
| Threat Actor | Location | Resources | Sophistication | Possible Motivations |
|---|---|---|---|---|
| Nation state | External | Extensive | Very high | Data exfiltration, philosophical, revenge, disruption, war |
| Unskilled | External | Limited | Very low | Disruption, data exfiltration, philosophical beliefs |
| Hacktivist | External | Some funding | Can be high | Philosophical beliefs, revenge, disruption/chaos |
| Insider threat | Internal | Many resources | Medium | Revenge, financial gain |
| Organized crime | External | Often extensive | Very high | Financial |
| Shadow IT | Internal | Many resources | Limited | Philosophical beliefs, revenge |
---

## 2.2 Threat Vectors and Attack Surfaces

---

### Common Threat Vectors
**Video length: 17:14**

### Key Concepts
- Threat Vetor - The method that an attacker uses to gain entry / acces to information, resorse, or location

### Notes
- Message based through email address -> link malware and phishing, SMS for links
- Phishing attacks, uses social egenering to gain info or money, malware can be embeded in websites through them running a script
- Also Image beased, for instant where the SVG format contains an .xml file which allows more info to be attached, injects/javascript
- File threat vectors, Executables are the easy ones but PDFs can contain scripting, ZIP/RAR compressed might also contain threats, Microsoft Office and macros. 
- Voice vectors, through calling, think voice cloning which is only more reliant in the age of AI, Spam over IP allows for lage scale calling
- Removable device vectors, USB drives which can be plugged in can contain malware, it can also act as a keybaord, running a script or macro
- Unsupported End of Life (EOL) vectors, no security patches on end of life software can create a risk of a vulnerabity is found
- Unsecure Network Vectors, wirelesss networks must use security protocols, proper authentication
- Open Service Ports, netowrk services connect over TCP/UDP ports, every port is an opportunity for attackers, every app = new open port = less security, firewall in/out rules can help a lot
- Defualt credentials must be change, (i.e. admin, password on a router)
- Supply chain vectors, say someone installs malware on a switch while it's being transported

---

### Phishing
**Video length: 6:32**

### Key Concepts
- Phishing - Social engeneering with spoofing, (email, text, etc)
- Pretexting - A made up story to make a phishing attack belivable

### Notes
- Very often delivered through email and text, ofen through links
- Typosquating are mistypes in links (go0gle.com/login)


---

### Impersonation
**Video length: 5:52**

### Key Concepts
- Impersonation - A type fo pretext where an attacker pretends to be someone they're not

### Notes
- Goals of impersonation are often to get information that the attacker didn't prior have access to (SSN, Banking, Credit)
- Identiy fraud is a major part of impersonation, someone pretends to be you can be used to 
    - Open a credit card in your name, open a bank account -> loan fraud
    - Dont give away any personal information, always verify someone if unsure

---
                                                                                                      
### Watering Hole Attacks
**Video length: 4:12**

### Key Concepts


### Notes
- A watering hole attack is when instead of goning for the main target, the attacker will go for a 3rd party company, in hopes the target accesses it.
- To try to prevent this you're security strategy should have multiple layers of defense (defense in depth)

---

### Other Social Engineering Attacks
**Video length: 3:29**

### Key Concepts
- Misinformation / Disinformation - fake or made up information used to persuade, distract, or create conflict

### Notes
- Brand name impersonations can be used to make users think a brand said or did something when in reality it was an attacker trying to use the name or logo

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
|      |            |

---

## Section 2 — Practice Exam Weak Areas
-
