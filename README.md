<div align="center">

<svg width="800" height="340" viewBox="0 0 800 340" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <radialGradient id="globeGrad" cx="42%" cy="38%" r="58%">
      <stop offset="0%" stop-color="#003a52"/>
      <stop offset="60%" stop-color="#001520"/>
      <stop offset="100%" stop-color="#000508"/>
    </radialGradient>
    <radialGradient id="glowGrad" cx="50%" cy="50%" r="50%">
      <stop offset="0%" stop-color="#00d4ff" stop-opacity="0.2"/>
      <stop offset="100%" stop-color="#00d4ff" stop-opacity="0"/>
    </radialGradient>
    <filter id="glow">
      <feGaussianBlur stdDeviation="3" result="blur"/>
      <feMerge><feMergeNode in="blur"/><feMergeNode in="SourceGraphic"/></feMerge>
    </filter>
    <filter id="textGlow">
      <feGaussianBlur stdDeviation="5" result="blur"/>
      <feMerge><feMergeNode in="blur"/><feMergeNode in="blur"/><feMergeNode in="SourceGraphic"/></feMerge>
    </filter>
    <clipPath id="globeClip">
      <circle cx="118" cy="170" r="90"/>
    </clipPath>
  </defs>

  <!-- Background -->
  <rect width="800" height="340" fill="#000810"/>

  <!-- Star field -->
  <g fill="#ffffff" opacity="0.3">
    <circle cx="310" cy="25" r="0.8"/><circle cx="450" cy="18" r="0.6"/><circle cx="560" cy="30" r="0.7"/>
    <circle cx="650" cy="15" r="0.5"/><circle cx="720" cy="40" r="0.8"/><circle cx="380" cy="310" r="0.6"/>
    <circle cx="500" cy="300" r="0.7"/><circle cx="600" cy="320" r="0.5"/><circle cx="680" cy="295" r="0.8"/>
    <circle cx="260" cy="290" r="0.6"/><circle cx="760" cy="280" r="0.5"/><circle cx="740" cy="60" r="0.6"/>
    <circle cx="340" cy="45" r="0.5"/><circle cx="420" cy="295" r="0.6"/><circle cx="770" cy="160" r="0.5"/>
  </g>

  <!-- Globe outer glow -->
  <circle cx="118" cy="170" r="112" fill="url(#glowGrad)"/>

  <!-- Globe body -->
  <circle cx="118" cy="170" r="90" fill="url(#globeGrad)" stroke="#00d4ff" stroke-width="1.2" opacity="0.95"/>

  <!-- Globe latitude lines (static, clipped) -->
  <g clip-path="url(#globeClip)" stroke="#00d4ff" stroke-width="0.5" fill="none" opacity="0.4">
    <ellipse cx="118" cy="170" rx="90" ry="20"/>
    <ellipse cx="118" cy="170" rx="90" ry="46"/>
    <ellipse cx="118" cy="170" rx="90" ry="70"/>
    <line x1="28" y1="170" x2="208" y2="170"/>
  </g>

  <!-- Rotating longitude lines -->
  <g clip-path="url(#globeClip)" stroke="#00d4ff" stroke-width="0.6" fill="none" opacity="0.45">
    <ellipse cx="118" cy="170" rx="18" ry="90">
      <animateTransform attributeName="transform" type="rotate" from="0 118 170" to="360 118 170" dur="7s" repeatCount="indefinite"/>
    </ellipse>
    <ellipse cx="118" cy="170" rx="45" ry="90">
      <animateTransform attributeName="transform" type="rotate" from="0 118 170" to="360 118 170" dur="7s" repeatCount="indefinite"/>
    </ellipse>
    <ellipse cx="118" cy="170" rx="72" ry="90">
      <animateTransform attributeName="transform" type="rotate" from="0 118 170" to="360 118 170" dur="7s" repeatCount="indefinite"/>
    </ellipse>
    <ellipse cx="118" cy="170" rx="90" ry="90">
      <animateTransform attributeName="transform" type="rotate" from="0 118 170" to="360 118 170" dur="7s" repeatCount="indefinite"/>
    </ellipse>
  </g>

  <!-- Scan sweep on globe -->
  <g clip-path="url(#globeClip)">
    <rect x="28" y="128" width="180" height="16" fill="#00d4ff" opacity="0.07">
      <animate attributeName="y" from="80" to="260" dur="2.8s" repeatCount="indefinite"/>
    </rect>
  </g>

  <!-- Pulsing target dots -->
  <g filter="url(#glow)">
    <circle cx="90" cy="148" r="3.5" fill="#00ff88">
      <animate attributeName="r" values="3.5;5.5;3.5" dur="2s" repeatCount="indefinite"/>
      <animate attributeName="opacity" values="1;0.4;1" dur="2s" repeatCount="indefinite"/>
    </circle>
    <circle cx="148" cy="188" r="3" fill="#ff2d55">
      <animate attributeName="r" values="3;4.5;3" dur="1.8s" repeatCount="indefinite"/>
      <animate attributeName="opacity" values="1;0.3;1" dur="1.8s" repeatCount="indefinite"/>
    </circle>
    <circle cx="105" cy="200" r="2.5" fill="#ffb700">
      <animate attributeName="opacity" values="0.3;1;0.3" dur="2.5s" repeatCount="indefinite"/>
    </circle>
    <circle cx="135" cy="152" r="2.5" fill="#00d4ff">
      <animate attributeName="opacity" values="1;0.3;1" dur="1.4s" repeatCount="indefinite"/>
    </circle>
    <circle cx="78" cy="178" r="2.8" fill="#b44bff">
      <animate attributeName="r" values="2.8;4;2.8" dur="2.2s" repeatCount="indefinite"/>
      <animate attributeName="opacity" values="0.5;1;0.5" dur="2.2s" repeatCount="indefinite"/>
    </circle>
  </g>

  <!-- Target rings -->
  <circle cx="90" cy="148" r="10" fill="none" stroke="#00ff88" stroke-width="0.8">
    <animate attributeName="r" values="6;16;6" dur="2s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="0.7;0;0.7" dur="2s" repeatCount="indefinite"/>
  </circle>
  <circle cx="148" cy="188" r="8" fill="none" stroke="#ff2d55" stroke-width="0.8">
    <animate attributeName="r" values="5;13;5" dur="1.8s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="0.7;0;0.7" dur="1.8s" repeatCount="indefinite"/>
  </circle>

  <!-- Connection arcs globe → right -->
  <g fill="none" filter="url(#glow)">
    <path d="M200 148 Q285 88 365 128" stroke="#00ff88" stroke-width="0.9">
      <animate attributeName="stroke-dasharray" values="0,260;260,0" dur="3.5s" repeatCount="indefinite"/>
      <animate attributeName="opacity" values="0;0.8;0" dur="3.5s" repeatCount="indefinite"/>
    </path>
    <path d="M205 190 Q290 235 370 200" stroke="#ff2d55" stroke-width="0.9">
      <animate attributeName="stroke-dasharray" values="0,260;260,0" dur="4.2s" repeatCount="indefinite"/>
      <animate attributeName="opacity" values="0;0.7;0" dur="4.2s" repeatCount="indefinite"/>
    </path>
    <path d="M200 168 Q300 168 370 165" stroke="#00d4ff" stroke-width="0.6" stroke-dasharray="4,4">
      <animate attributeName="opacity" values="0.15;0.5;0.15" dur="2s" repeatCount="indefinite"/>
    </path>
  </g>

  <!-- Vertical separator -->
  <line x1="232" y1="48" x2="232" y2="292" stroke="#00d4ff" stroke-width="0.5" opacity="0.2"/>

  <!-- TOP LABEL -->
  <text x="252" y="78" font-family="'Courier New',monospace" font-size="10" fill="#00d4ff" opacity="0.5" letter-spacing="5">// APPLICATION SECURITY RESEARCHER //</text>

  <!-- RAJESHWAR -->
  <text x="250" y="162" font-family="'Courier New',monospace" font-size="54" font-weight="bold" fill="#00d4ff" letter-spacing="3" filter="url(#textGlow)">RAJESHWAR</text>

  <!-- SINGH -->
  <text x="253" y="220" font-family="'Courier New',monospace" font-size="54" font-weight="bold" fill="#ffffff" letter-spacing="3" filter="url(#textGlow)">SINGH</text>

  <!-- Animated underline -->
  <rect x="250" y="230" width="0" height="1.5" fill="#00d4ff" rx="1" opacity="0.85">
    <animate attributeName="width" from="0" to="510" dur="1.2s" fill="freeze" begin="0.3s"/>
  </rect>

  <!-- Subtitle row -->
  <text x="253" y="258" font-family="'Courier New',monospace" font-size="11.5" fill="#1a4a60" letter-spacing="2">APPSEC</text>
  <text x="322" y="258" font-family="'Courier New',monospace" font-size="11.5" fill="#00d4ff" opacity="0.55">▸</text>
  <text x="337" y="258" font-family="'Courier New',monospace" font-size="11.5" fill="#1a4a60" letter-spacing="2">DAST EXPERT</text>
  <text x="448" y="258" font-family="'Courier New',monospace" font-size="11.5" fill="#00d4ff" opacity="0.55">▸</text>
  <text x="463" y="258" font-family="'Courier New',monospace" font-size="11.5" fill="#1a4a60" letter-spacing="2">CVE HUNTER</text>

  <!-- Badges row -->
  <rect x="250" y="270" width="180" height="26" rx="3" fill="rgba(0,212,255,0.05)" stroke="#00ff88" stroke-width="0.7" opacity="0.8"/>
  <text x="263" y="287" font-family="'Courier New',monospace" font-size="11" fill="#00ff88" letter-spacing="2" filter="url(#glow)">[ 100+ CVEs DISCLOSED ]</text>

  <rect x="444" y="270" width="140" height="26" rx="3" fill="rgba(0,212,255,0.04)" stroke="#00d4ff" stroke-width="0.7" opacity="0.6"/>
  <text x="456" y="287" font-family="'Courier New',monospace" font-size="11" fill="#2a6080" letter-spacing="2">📍 BANGALORE, IN</text>

  <!-- Blinking cursor -->
  <rect x="648" y="196" width="9" height="24" fill="#00d4ff" opacity="0.85" rx="1">
    <animate attributeName="opacity" values="0.85;0;0.85" dur="1s" repeatCount="indefinite"/>
  </rect>

  <!-- Corner brackets -->
  <g stroke="#00d4ff" stroke-width="1" fill="none" opacity="0.3">
    <path d="M6 6 L6 26 L26 26"/>
    <path d="M794 6 L794 26 L774 26"/>
    <path d="M6 334 L6 314 L26 314"/>
    <path d="M794 334 L794 314 L774 314"/>
  </g>
</svg>

### `> Application Security Researcher // Threat Hunter // DAST Expert`

[![Typing SVG](https://readme-typing-svg.demolab.com?font=Share+Tech+Mono&size=15&pause=1000&color=00D4FF&center=true&vCenter=true&width=600&lines=100%2B+CVEs+Discovered+%26+Responsibly+Disclosed;Application+Security+%7C+DAST+%7C+Threat+Research;Vulnerability+Assessment+%7C+Penetration+Testing;Bug+Bounty+Hunter+%7C+Bangalore%2C+India)](https://github.com/Rajeshwar40)

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Rajeshwar_Singh-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/rajeshwar-singh-59070715b/)
[![GitHub](https://img.shields.io/badge/GitHub-Rajeshwar40-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Rajeshwar40)
[![Email](https://img.shields.io/badge/Email-rajeshwar432@gmail.com-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:rajeshwar432@gmail.com)
[![Location](https://img.shields.io/badge/Location-Bangalore,_India-00D4FF?style=for-the-badge&logo=googlemaps&logoColor=white)](https://github.com/Rajeshwar40)

</div>

---

## `> whoami`

```bash
$ cat /etc/researcher.conf

Name        : Rajeshwar Singh
Role        : Application Security Researcher
Speciality  : DAST | Web App Pentesting | Threat Research
CVEs        : 100+ Discovered & Responsibly Disclosed
Location    : Bangalore, India
Status      : [ ● AVAILABLE ] Open for new engagements
Contact     : rajeshwar432@gmail.com | +91 9906041418
```

> I hunt vulnerabilities so you don't have to deal with breaches. Application security researcher specializing in **Dynamic Application Security Testing (DAST)**, web application penetration testing, and responsible vulnerability disclosure across multiple CVE years (2020–2026).

---

## `> cat cve_stats.json`

<div align="center">

| 📅 Year | 🔢 CVEs Disclosed |
|:-------:|:-----------------:|
| 2020    | CVE-2020-15035 → 15037 |
| 2022    | CVE-2022-29004 → 47102 series |
| 2023    | CVE-2023-23122 → 51352 series |
| 2024    | CVE-2024-29340 → 55478 series |
| 2025    | CVE-2025-26208 → 69533 series |
| 2026    | Reserved (Upcoming) |

</div>

### Notable CVEs

| CVE ID | CVSS | Severity | Category |
|--------|------|----------|----------|
| `CVE-2022-45730` | 9.1 | 🔴 HIGH | SQL Injection |
| `CVE-2022-45214` | 8.8 | 🔴 HIGH | Web Application |
| `CVE-2022-46957` | 8.8 | 🔴 HIGH | Authentication Bypass |
| `CVE-2022-45215` | 8.1 | 🔴 HIGH | Access Control |
| `CVE-2022-46624` | 6.1 | 🟡 MEDIUM | Cross-Site Scripting |
| `CVE-2022-45218` | 5.3 | 🟡 MEDIUM | Information Disclosure |

> 🔗 Full disclosure list available on [NVD/NIST](https://nvd.nist.gov/vuln/search)

---

## `> ls -la skills/`

```
drwxr-xr-x  Application Security
drwxr-xr-x  Dynamic Application Security Testing (DAST)
drwxr-xr-x  Web Application Penetration Testing
drwxr-xr-x  Vulnerability Assessment & Reporting
drwxr-xr-x  Threat Research & Intelligence
drwxr-xr-x  Digital Fraud Prevention
drwxr-xr-x  Source Code Review
drwxr-xr-x  API Security Testing
drwxr-xr-x  OWASP Top 10
drwxr-xr-x  CVE Research & Responsible Disclosure
```

---

## `> cat tools.txt`

<div align="center">

![Burp Suite](https://img.shields.io/badge/Burp_Suite-FF6633?style=for-the-badge&logo=burpsuite&logoColor=white)
![OWASP ZAP](https://img.shields.io/badge/OWASP_ZAP-00549E?style=for-the-badge&logo=owasp&logoColor=white)
![Metasploit](https://img.shields.io/badge/Metasploit-2596CD?style=for-the-badge&logo=metasploit&logoColor=white)
![Nmap](https://img.shields.io/badge/Nmap-004088?style=for-the-badge&logo=nmap&logoColor=white)
![Kali Linux](https://img.shields.io/badge/Kali_Linux-557C94?style=for-the-badge&logo=kalilinux&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Bash](https://img.shields.io/badge/Bash-4EAA25?style=for-the-badge&logo=gnubash&logoColor=white)
![Wireshark](https://img.shields.io/badge/Wireshark-1679A7?style=for-the-badge&logo=wireshark&logoColor=white)
![SQLMap](https://img.shields.io/badge/SQLMap-CC0000?style=for-the-badge&logoColor=white)
![Nessus](https://img.shields.io/badge/Nessus-00C176?style=for-the-badge&logoColor=white)

</div>

---

## `> ./methodology.sh`

```
[PHASE 1] RECONNAISSANCE
  → Passive & Active Information Gathering
  → Attack Surface Mapping
  → Technology Stack Fingerprinting

[PHASE 2] VULNERABILITY DISCOVERY
  → DAST Scanning (Automated + Manual)
  → Business Logic Analysis
  → Authentication & Authorization Testing
  → Injection Vulnerability Testing (SQLi, XSS, SSTI...)

[PHASE 3] EXPLOITATION & VALIDATION
  → Proof-of-Concept Development
  → Impact Assessment
  → CVSS Scoring

[PHASE 4] RESPONSIBLE DISCLOSURE
  → Vendor Notification
  → CVE Assignment via MITRE/NVD
  → Public Disclosure (Post-patch)
```

---

## `> cat domains.txt`

```yaml
primary_focus:
  - Web Application Security
  - API Security Testing
  - Authentication Bypass
  - SQL Injection
  - Cross-Site Scripting (XSS)
  - IDOR & Access Control Flaws
  - Information Disclosure
  - Business Logic Vulnerabilities

secondary_focus:
  - Digital Fraud Prevention
  - Threat Intelligence
  - Security Research & Publishing
  - CVE Reporting & Documentation
```

---

## `> ping rajeshwar`

```bash
$ ping rajeshwar432@gmail.com

PING rajeshwar432@gmail.com ...
64 bytes: seq=1 ttl=64 time=<fast> ms   ✓
Response: AVAILABLE FOR ENGAGEMENTS

Available for:
  [✓] Application Security Consulting
  [✓] Penetration Testing Projects
  [✓] Bug Bounty Collaborations
  [✓] Security Research Partnerships
  [✓] Full-time / Contract Roles
```

<div align="center">

[![Email](https://img.shields.io/badge/Drop_a_Mail-rajeshwar432@gmail.com-00D4FF?style=for-the-badge&logo=gmail&logoColor=white)](mailto:rajeshwar432@gmail.com)
[![LinkedIn](https://img.shields.io/badge/Connect_on_LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/rajeshwar-singh-59070715b/)
[![Phone](https://img.shields.io/badge/Call-+91_9906041418-25D366?style=for-the-badge&logo=whatsapp&logoColor=white)](tel:+919906041418)

</div>

---

<div align="center">

```
┌─────────────────────────────────────────────────────────────┐
│   "Security is not a product, but a process."               │
│                                          — Bruce Schneier   │
│                                                             │
│   [ Rajeshwar Singh // AppSec Researcher // Bangalore ]     │
└─────────────────────────────────────────────────────────────┘
```

![Profile Views](https://komarev.com/ghpvc/?username=Rajeshwar40&color=00d4ff&style=for-the-badge&label=PROFILE+VIEWS)

*All CVEs discovered and reported through responsible disclosure. Details available on [NVD/NIST](https://nvd.nist.gov).*

</div>
