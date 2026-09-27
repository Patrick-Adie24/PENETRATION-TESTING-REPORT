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

### Example Hosts Identified

```text
10.0.0.1
10.0.0.4
10.0.0.19
10.0.0.5
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
