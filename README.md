<div align="center">

# 🛡️ PENETRATION TESTING REPORT

### 🔎 FOOTPRINTING & NETWORK SCANNING PHASES

![Cybersecurity](https://img.shields.io/badge/Cybersecurity-black)
![Kali Linux](https://img.shields.io/badge/OS-Kali%20Linux-blue)
![Status](https://img.shields.io/badge/Status-Inprogress-yellow)
![Networkwalks](https://img.shields.io/badge/Networkwalks-B083-orange)
![Authorized](https://img.shields.io/badge/Authorized-Yes-white)

**W2-PM-FINAL | CYBERSECURITY | NETWORKWALKS**
### 👨‍💻 Adie Patrick Betiang
**Cybersecurity Professional | Networkwalks Intern | Batch B083**

---

</div>

## 🛡️ Scope of Work Review

| **Category** | **Details** |
|---|---|
| 👤 **Pentester** | Adie Patrick Betiang |
| 🎓 **Program / Batch** | B083 Networkwalks |
| 📅 **Assessment Date** | 18 September 2026 |
| 🧪 **Modules Completed** | W2-PM1 Multiple Kali Tools<br>W2-PM5 Zenmap Scanning |
| 🎯 **Assessment Targets** | Networkwalks Authorized Target<br>microsoft.com (public OSINT reconnaissance only)<br>My Own Local LAN Network |
| 🔐 **Authorization** | Written Permission Secured |
| 🔎 **Phase 1** | Reconnaissance & Footprinting |
| 🌐 **Phase 2** | Scanning & Network Discovery |
| 🚧 **Phases 3–5** | In Progress |
| 🖥️ **Primary Platforms** | Kali Linux & Windows |

---

# 🛡️ 1. Liability & Authorization Disclaimer

> **AUTHORIZED SECURITY TESTING ONLY**

All activities documented in this report were performed only against systems and devices for which I had appropriate authorization, including systems belonging to me.

This project is intended strictly for **educational, cybersecurity research, ethical hacking, and professional development purposes**.

Unauthorized access, scanning, enumeration, exploitation, or interference with computer systems may violate applicable laws and regulations.

**Do not use the techniques, commands, or information contained in this repository against systems without explicit authorization.**

The author, instructor, and Networkwalks are not responsible for misuse of the information contained within this project.

> 🛡️ **Security principle:** Always define and respect the authorized scope before performing reconnaissance or security testing.

---

# 📌 2. Introduction

This repository documents a Week 2 practical cybersecurity project completed as part of the **Networkwalks Cybersecurity Internship Program – Batch B082**.

The project focuses on practical reconnaissance and network-scanning techniques using **Kali Linux**.

The project covers:

- 🌐 Domain Footprinting
- 🔎 Passive OSINT Reconnaissance
- 🖥️ Web Technology Fingerprinting
- 🌍 DNS Enumeration
- 📡 Network Discovery
- 🔗 OSINT Link Analysis
- 📊 Security Risk Analysis

The activities were performed against authorized targets, publicly available information sources, and the tester's own local network.

Each activity was documented with:

- 🖥️ Command/tool used
- 📊 Observed result
- 📸 Supporting evidence
- 🔎 Security relevance
- ⚠️ Potential risk
- 🛡️ Recommended mitigation

---

# 🛡️ 3. Tools & Technologies

| **Tool / Technology** | **Purpose** |
|---|---|
| 🐉 **Kali Linux** | Security testing and reconnaissance environment |
| 🪟 **Windows** | Local network identification and Zenmap environment |
| 🔍 **WHOIS** | Domain registration and name-server information |
| 🌐 **WhatWeb** | Web technology and CMS fingerprinting |
| 📡 **Nslookup** | DNS resolution and IP identification |
| 📥 **curl** | HTTP response header analysis |
| 🛡️ **Wafw00f** | Web Application Firewall identification |
| 🗂️ **DNSRecon** | DNS record enumeration |
| 🛰️ **Zenmap / Nmap GUI** | Network discovery and host scanning |
| 🕵️‍♂️ **theHarvester 4.10.1** | Passive OSINT collection |
| 🗺️ **Maltego CE 4.12.1** | OSINT and relationship analysis |
| 💻 **Windows CMD** | Local IP and MAC address identification |

---

# 🛡️ 4. Activities Performed

## 4.1 🔍 Footprinting & Reconnaissance

Authorized reconnaissance was conducted against the **networkwalks.com** domain utilizing six specialized tools within the Kali Linux:

```text
WHOIS
WhatWeb
Nslookup
curl
Wafw00f
DNSRecon
```

Each tool provided a different perspective of the target's publicly observable infrastructure.

---

### 🔹 4.1.1 WHOIS

WHOIS was used to collect publicly available domain registration information and identify relevant domain infrastructure, including name-server information.

```text
The domain is registered through GoDaddy with WHOIS privacy enabled via Domains By Proxy
The true registrant's identity and contact details are not publicly exposed.
```

**Security relevance:**

WHOIS information can provide an initial understanding of how a domain is registered and which infrastructure is associated with it.

---

### 🔹 4.1.2 WhatWeb

WhatWeb was used to fingerprint technologies exposed by the website.

The observed results identified technologies including:

```text
WordPress 7.1.1
WP Download Manager plugin (v3.3.58)
```

**Security relevance:**

Technology and version information can assist security professionals in identifying software that may require additional security review.

> 🛡️ Technology identification does **not** automatically indicate that a vulnerability exists.

---

### 🔹 4.1.3 Nslookup

Nslookup was used to resolve the target domain to its associated IP address.

```text
nslookup networkwalks.com
```

**Observed result:**

```text
192.232.216.135
```

**Security relevance:**

IP resolution provides information about the network location associated with a web service and may support further authorized infrastructure analysis.

---

### 🔹 4.1.4 cURL

The following HTTP-header inspection technique was used:

```bash
curl -I networkwalks.com
```

The response provided additional information about the web application and exposed the following REST API endpoint:

```text
/wp-json/
```

**Security relevance:**

HTTP response information can assist with technology fingerprinting and further authorized enumeration.

---

### 🔹 4.1.5 Wafw00f

Wafw00f was used to determine whether a Web Application Firewall was protecting the target.

```text
wafw00f networkwalks.com
```

**Observed result:**

```text
ModSecurity (SpiderLabs)Web Application Firewall
```

**Security relevance:**

Identifying defensive technologies can help security professionals understand the security architecture protecting a web application.

---

### 🔹 4.1.6 DNSRecon

DNSRecon was used to enumerate publicly accessible DNS information.

```text
dnsrecon -d networkwalks.com
```

The activity provided information relating to:

- Name servers
- Mail servers
- SPF / TXT records
- Service records
- DNS-related information

**Security relevance:**

DNS information can help create a broader understanding of an organization's publicly exposed infrastructure.

---

# 🛡️ 4.2 OSINT Reconnaissance with theHarvester

`` theHarvester `` was used to gather publicly available information about:

`` microsoft.com ``

Full reconnaissance run used for this report:

```text
theHarvester -d microsoft.com -l 50 -b all
```

The exercise collected publicly available information including:

- ASNs
- IP addresses
- Email addresses
- Hostnames
- Subdomains
- Interesting URLs

| **Category	Result** | **Result** |
|---|---|
| **ASNs found** | 8 |
| **IP addresses found** | 52 unique IPv4/IPv6 addresses associated with microsoft.com infrastructure |
| **Email addresses found** | 3  (dotnet-docker-bot@microsoft.com, opencode@microsoft.com, secure@microsoft.com) |
| **Hosts / subdomains found** | Hosts / subdomains found	9,969 host names enumerated <br>(large mix of production, corporate, and internal-looking hostnames) |
| **Interesting URLs found** | 2  — an Azure AD / Microsoft Entra OAuth2 authorize URL referencing a Cloudflare Access endpoint <br>the Microsoft privacy statement page |

> **Important:** The hostname results were collected from available public OSINT sources and do not by themselves indicate that every discovered hostname is directly accessible or vulnerable.

---

# 🛡️ 4.3 Network Scanning with Zenmap

A local network discovery scan was performed against the authorized local subnet.

The objective was to:

- Identify the local IP address
- Determine the local subnet
- Discover active hosts
- Identify IP addresses
- Identify MAC addresses
- Generate a network topology

The Windows `ipconfig` command was first used to identify the local network configuration.

The identified subnet was then entered into Zenmap.

Command:

```text
> nmap -sn 192.168.100.21/24
```

The scan identified:

```text
> 13 Live Hosts
```

The scan was used to identify active devices on the local network.

### Example Hosts Identified:

```text
192.168.100.1
192.168.100.7
192.168.100.80
192.168.100.99
192.168.100.114
```

The practical example also identified associated MAC addresses.

After completing the scan, the **Topology** section in Zenmap was used to visualize the discovered network.

The topology legend was enabled and the resulting network topology was saved in PDF format as required by the practical exercise.

> **Important:** The addresses above represent the example results supplied for the practical. When submitting the final assessment, they should be replaced with the actual results from my authorized local network.

---

# 🛡️ 4.4 OSINT Link Analysis with Maltego

Maltego Community Edition 4.12.1 was used to perform graph-based OSINT analysis.

The investigation established a relationship between the target domain and a publicly identified email address.

```text
networkwalks.com
       │
       ▼
info@networkwalks.com
       │
       ▼
Public Search Result
```

Maltego was also used to expand the email entity through available search-engine transforms.

---
# 🛡️ 4.5  Footprinting with the Google Hacking Database (GHDB)

**Google Hacking (Dorking)** uses advanced search operators to find hidden, publicly accessible data without directly interacting with the target.

It highlights the security implications of misconfigured internet-facing IoT devices and exposed document.

## Tools & Resources
 
| Tool / Resource | Purpose |
|---|---|
| [Google Search](https://www.google.com) | Executing dork queries |
| [Exploit-DB GHDB](https://www.exploit-db.com/google-hacking-database) | Source of dork syntax, categorized by type |
| Browser (Chrome) | Verifying and viewing results |

## Task 1: Exposed Security Camera Feeds
 
**Goal:** Find 10 live, publicly accessible security camera links using GHDB dorks.
 
| No. | Link | Dork Used | Username / Password |
|---|---|---|---|
| 1 | `http://122.116.41.8:8080/` | `intitle:"webcamXP" inurl:8080` | — |
| 2 | `http://99.114.240.169:8080/` | `intitle:"Webcam" inurl:WebCam.htm` | — |
| 3 | `skylinewebcams.com` — Piazza di Spagna / Piazza Cavour, Rome | `inurl:webcam site:skylinewebcams.com inurl:roma` | — |

## Task 2: Downloadable Mathematics eBooks (PDF)
 
**Goal:** Find 10 open directory listings containing downloadable mathematics eBooks in PDF format.
 
| No. | Link | Dork Used |
|---|---|---|
| 1 | `https://www.skylineuniversity.ac.ae/pdf/math/` | `intitle:index.of "parent directory" mathematics pdf` |
| 2 | `https://education.giakonda.org.uk/Maths/Additional_Mathematics__Pure_and_Applied.pdf` | *(same category — open index)* |
| 3 | `http://erewhon.superkuh.com/library/Math/` | *(same category — open index)* |
| 4 | `https://www.netlib.org/math/docpdf/` | *(same category — open index)* |
| 5 | `http://inis.jinr.ru/sl/vol2/Mathematics/Math.Encyclopedia/Pdf/` | *(same category — open index)* |
| 6 | `https://naac.matagujricollege.org/Syllabus/2016-17/Mathematics/syllabus2016-17/` | *(same category — open index)* |
| 7 | `https://lira.epac.to/DOCS-TECH/Math/Engineering%20and%20Applied/` | *(same category — open index)* |
| 8 | `https://docs.bartonccc.edu/syllabus/Master/MATH/` | *(same category — open index)* |
| 9 | `https://www.math.utah.edu/~cherk/teach/5740MathModeling/12mathmodel/sources/` | *(same category — open index)* |
| 10 | `http://www.issp.ac.ru/ebooks/books/open/` | *(same category — open index)* |

---
# 🛡️ 5. Risk Analysis & Impact

The following observations were identified during the footprinting and network discovery activities.

| # | 🔎 Finding | 📊 Evidence / Observation | ⚠️ Potential Impact | Risk |
|---:|---|---|---|---|
| 1 | Web technology information exposed | WhatWeb identified WordPress and WP Download Manager | Could assist technology fingerprinting and further security review | 🟠 **Medium** |
| 2 | Server IP identifiable | Nslookup resolved the domain to `192.232.216.135` | Provides information about the network location of the web service | 🟢 **Low** |
| 3 | HTTP technical information exposed | curl returned HTTP headers and exposed `/wp-json/` | May assist fingerprinting and further enumeration | 🟢 **Low** |
| 4 | WAF technology identifiable | Wafw00f identified ModSecurity | Reveals information about the web application's defensive architecture | 🟢 **Low** |
| 5 | DNS infrastructure information exposed | DNSRecon identified DNS, mail and service records | Can assist in building an infrastructure profile | 🟠 **Medium** |
| 6 | Employee/functional email addresses exposed | theHarvester identified 3 email addresses tied to engineering/operations functions at microsoft.com | Usable for phishing, spear-phishing, or credential-stuffing target lists | 🟢 **Low** |
| 7 | Cloud/network infrastructure identifiable via ASN and IP data | 8 ASNs and 52 IP addresses were enumerated | an attacker map network ownership and hosting  | 🟢 **Low** |
| 8 | Authentication/SSO endpoint discoverable | An indexed Microsoft Entra ID (Azure AD) OAuth2 authorize URL referencing a third-party Cloudflare  | Publicly indexed auth/SSO URLs can reveal third-party integrations and potential phishing/redirect abuse | 🟢 **Low** |
| 9 | Multiple live hosts visible | Zenmap identified thirteen hosts in the example network | Unknown devices may represent unauthorized or unmanaged assets | 🟠 **Medium** |

### Risk Rating Key

| Indicator | Severity |
|---|---|
| 🔴 | **Critical** |
| 🟠 | **Medium** |
| 🟢 | **Low** |

> **Important Assessment Note:**  
> These findings represent observations from reconnaissance and network discovery activities. They are **not confirmed vulnerabilities**.

No exploitation or vulnerability validation was performed during these two modules.

The presence of a software version, IP address, DNS record, or HTTP endpoint does not by itself prove that a system is vulnerable.

Additional authorized security testing would be required to validate any suspected vulnerability.

---
# 🛡️ 6. Recommendations

Based on the observations collected during the assessment, the following security improvements are recommended.

### 1️⃣ Review Publicly Exposed Technology Information

Organizations should regularly review publicly exposed information relating to their CMS platforms, plugins, frameworks, and web technologies.

### 2️⃣ Maintain Updated Software

CMS platforms, plugins, frameworks, and other technologies should be regularly updated and monitored against current security advisories.

### 3️⃣ Review HTTP Response Headers

HTTP response headers should be reviewed to determine whether unnecessary technical information is being exposed.

### 4️⃣ Review DNS Records

DNS records should be periodically reviewed to ensure that only required information and services are publicly exposed.

### 5️⃣ Properly Configure & Monitor the WAF

The Web Application Firewall should remain enabled, properly configured, monitored, and regularly tuned according to the organization's security requirements.

### 6️⃣ Perform Regular Internal Network Discovery

Organizations should periodically scan their authorized internal networks to identify active devices and maintain visibility of their infrastructure.

### 7️⃣ Investigate Unknown Devices

Unexpected devices identified during network discovery should be investigated and verified.

### 8️⃣ Maintain Network Documentation

Network topology, IP addresses, devices, and infrastructure documentation should be maintained and updated regularly.

### 9️⃣ Perform Security Testing Within an Authorized Scope

All reconnaissance, scanning, enumeration, and security testing should be performed only against systems and networks where appropriate authorization has been obtained.

---
# 🛡️ 7. Security Assessment Summary

| **Assessment Area** | **Status** |
|---|---|
| 🔎 Reconnaissance | ✅ Completed |
| 🌐 Footprinting | ✅ Completed |
| 🛰️ Network Discovery | ✅ Completed |
| 🖥️ Host Identification | ✅ Completed |
| 🗺️ Network Topology | ✅ Completed |
| 💥 Exploitation | ⏳ Not Performed |
| 🧪 Vulnerability Validation | ⏳ Not Performed |
| 🚧 Advanced Testing | 🔄 In Progress |

### Overall Assessment

```text
RECONNAISSANCE       ████████████████████ 100%
FOOTPRINTING         ████████████████████ 100%
NETWORK DISCOVERY    ████████████████████ 100%
EXPLOITATION         ░░░░░░░░░░░░░░░░░░░░   0%
```

---

# 🛡️ 8. Key Learning Outcomes

Through these practical exercises, I developed hands-on experience with:

- 🔎 Reconnaissance methodology
- 🌐 Domain footprinting
- 🧩 Web technology fingerprinting
- 📡 DNS enumeration
- 🛡️ WAF identification
- 🛰️ Network discovery
- 🖥️ Host identification
- 📍 IP and MAC address analysis
- 🗺️ Network topology visualization
- 📝 Professional security documentation
- ⚖️ Authorized security testing principles

The exercises demonstrated how much information can be collected before exploitation is even considered.

A cybersecurity professional must therefore understand both **how information can be discovered** and **how organizations can reduce unnecessary exposure**.

---

# 🛡️ 9. Conclusion

During **Week 2 of my Cybersecurity & Ethical Hacking internship at Networkwalks**, I completed practical activities covering **reconnaissance, footprinting, and network scanning**.

During the footprinting phase, I used multiple Kali Linux tools to collect and analyze publicly observable information about the target domain.

I learned how:

```text
WHOIS       → Domain information
WhatWeb     → Web technology fingerprinting
Nslookup    → DNS / IP resolution
cURL        → HTTP header inspection
Wafw00f     → WAF identification
DNSRecon    → DNS enumeration
theHarvester → Cloud/network infrastructure identifiable via ASN and IP data
Maltego     → Identify Domain and Email
GHDB        → Advanced search operators for hidden and publicly accessible data
```

During the network scanning phase, I used **Zenmap** to discover active hosts within my authorized local network environment and examine IP, MAC address, and topology information.

The exercises reinforced an important cybersecurity principle:

> **Effective security testing begins with understanding the environment.**

I also learned the importance of documenting security findings professionally by clearly explaining:

```text
What was performed
        ↓
What was discovered
        ↓
Why it matters
        ↓
What risk it may create
        ↓
How the risk can be reduced
```

Most importantly, these exercises reinforced the requirement that reconnaissance and scanning must always be conducted within an **authorized scope**.

This project represents another step in my development as a cybersecurity professional and contributes to my ongoing practical experience in **ethical hacking, network security, reconnaissance, and security assessment**.

---

# 🛡️ 10. Evidence Collected

Evidence from the practical activities is included below.

### 🔎 Footprinting Evidence

<details>
<summary><b>WHOIS Results</b></summary>

<img width="1365" height="739" alt="W2-PM1-TASK 1 My results of whois" src="https://github.com/user-attachments/assets/8927b327-1393-4ab3-8a20-de59c0ef5c4f" />

</details>

<details>
<summary><b>WhatWeb Results</b></summary>

<img width="1365" height="722" alt="W2-PM1-TASK 2 My results of whatweb" src="https://github.com/user-attachments/assets/bb95915b-224a-40bc-9999-987eb4b8148c" />

</details>

<details>
<summary><b>Nslookup Results</b></summary>

<img width="1365" height="767" alt="W2-PM1-TASK 3 My results of  nslookup" src="https://github.com/user-attachments/assets/990feb97-e50c-4c36-8a19-4c1bd8a97356" />

</details>

<details>
<summary><b>cURL Results</b></summary>

<img width="1365" height="716" alt="W2-PM1-TASK 4 My results of curl" src="https://github.com/user-attachments/assets/4607a39a-0273-4052-b35a-6bfa7f166a30" />

</details>

<details>
<summary><b>Wafw00f Results</b></summary>

<img width="1358" height="763" alt="W2-PM1-TASK 5 My results of wafw00f" src="https://github.com/user-attachments/assets/dc1eb10b-541c-41ee-9085-40cbb5df8faa" />

</details>

<details>
<summary><b>DNSRecon Results</b></summary>

<img width="1366" height="691" alt="W2-PM1-TASK 6 My results of dnsrecon" src="https://github.com/user-attachments/assets/f4a2b650-cb29-4bd0-b92f-d075065959d2" />

</details>

### 🌐 Zenmap Evidence

<details>
<summary><b>Windows IP Configuration</b></summary>

<img width="1365" height="722" alt="Ipconfig" src="https://github.com/user-attachments/assets/e13537ef-b8d3-48b9-8be4-4625cfcd6436" />

</details>

<details>
<summary><b>Zenmap Ping Scan</b></summary>

_<img width="1363" height="729" alt="ping scan" src="https://github.com/user-attachments/assets/072b3373-d351-4cc3-bf7c-07ff28d1565e" />

</details>

<details>
<summary><b>Zenmap Host Discovery</b></summary>

<img width="1365" height="764" alt="Host !" src="https://github.com/user-attachments/assets/09f07033-3c63-4247-a96e-2e94d81aee93" />
<img width="1349" height="720" alt="Host 2" src="https://github.com/user-attachments/assets/acaa608f-1386-4436-bf70-6056808cb82d" />


</details>

<details>
<summary><b>Zenmap Network Topology</b></summary>

<img width="1365" height="727" alt="Topology" src="https://github.com/user-attachments/assets/0dd7fbe1-57f1-4086-840a-81c44cc013c8" />

</details>

---

# 🛡️ 11. Networkwalks Academy Quiz Assessment

As part of the Networkwalks Academy cybersecurity training program, I completed a short knowledge assessment covering concepts related to the practical modules and cybersecurity activities studied during the program.

### 🏆 Quiz Performance

| **Assessment** | **Details** |
|---|---|
| 🎓 **Academy** | Networkwalks Academy |
| 📚 **Program** | Cybersecurity |
| 📅 **Assessment Date** | August 2026 |
| 🧪 **Assessment Type** | Short Knowledge Quiz |
| 📊 **Score** | **[29% 10/10]** |
| ✅ **Result** | **Passed / Completed** |

### 📸 Score Evidence

<img width="1365" height="753" alt="1" src="https://github.com/user-attachments/assets/0f1b4787-01ef-4d9c-baa2-ae9f6c4d6f91" />
<img width="1365" height="766" alt="2" src="https://github.com/user-attachments/assets/58b8f42b-65f9-4d53-9dbb-2f9bdeab3d9d" />


> 🏅 **Achievement:** Successfully completed the Networkwalks Academy knowledge assessment as part of my cybersecurity training and practical learning journey.

---

### 🛡️ Learning Validation

The quiz provided an opportunity to validate my understanding of the cybersecurity concepts covered during the training, complementing the hands-on practical activities documented in this repository.

**Knowledge Assessment → Practical Lab → Evidence → Professional Documentation**


---

# 🛡️ Assessment Progress

```text
PHASE 1
Reconnaissance & Footprinting
████████████████████████████████  COMPLETED ✅

PHASE 2
Scanning & Network Discovery
████████████████████████████████  COMPLETED ✅

PHASE 3
Vulnerability Assessment
████████████████░░░░░░░░░░░░░░░░  IN PROGRESS 🔄

PHASE 4
Exploitation
░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░  PENDING ⏳

PHASE 5
Reporting & Remediation
░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░  PENDING ⏳
```

---

# 👨‍💻 Author

<div align="center">

### **Adie Patrick Betiang**

**Cybersecurity Professional | Networkwalks Intern | Batch B083**

[![LinkedIn]]()

[![GitHub]()](https://github.com/)

</div>

---

# 🛡️ Project Information

| **Project Detail** | **Information** |
|---|---|
| 🏢 **Program** | Cybersecurity Program Networkwalks |
| 📅 **Week** | Week 02 |
| 🎓 **Batch** | B083 |
| 🔐 **Project Type** | Authorized Penetration Testing Lab |
| 🔎 **Primary Focus** | Footprinting & Network Scanning |
| 🐉 **Primary OS** | Kali Linux |
| 🛰️ **Scanning Tool** | Zenmap / Nmap |
| 📊 **Assessment Status** | In Progress |
| 📁 **Repository** | GitHub |

---

<div align="center">

### 🛡️ CYBERSECURITY • ETHICAL HACKING • NETWORK SECURITY

**Learn → Practice → Analyze → Secure**

<br>

*W2-PM-FINAL | Networkwalks | B083 | September 2026*

</div>

---
