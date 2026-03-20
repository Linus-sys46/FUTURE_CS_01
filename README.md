# Vulnerability Assessment Report – scanme.nmap.org

## Project Overview
This repository contains a **vulnerability assessment** of the publicly accessible website `scanme.nmap.org`. The purpose of this project is to **identify potential security weaknesses** through passive, ethical scanning and configuration analysis, classify risks in a business-friendly way, and provide actionable remediation recommendations.

---

## Scope
- Public-facing services only  
- No authentication or login testing  
- No exploitation or active attacks performed  
- Passive reconnaissance and configuration analysis only  

---

## Tools Used
| Tool | Purpose |
|------|---------|
| **Nmap** | Port discovery, service detection, version enumeration |
| **OWASP ZAP (Passive Scan)** | Identify missing security headers, directory exposure, and cross-domain misconfigurations |
| **Firefox DevTools** | Inspect headers, cookies, and client-side configuration |

---

## Findings

### Nmap Findings
| Finding | Issue | Risk Level |
|---------|-------|-----------|
| Outdated SSH Service | OpenSSH 6.6.1 | Medium |
| Outdated Apache Web Server | Apache 2.4.7 | Medium |
| Unencrypted HTTP | No HTTPS enforced | Medium |
| Open Non-Standard Ports | Ports 9929, 31337 | Medium |
| Information Disclosure | Service/version banners | Low |

### OWASP ZAP Findings
| Finding | Issue | Risk Level |
|---------|-------|-----------|
| CSP Header Not Set | No Content Security Policy | Medium |
| Cross-Domain Misconfiguration | Access-Control-Allow-Origin not restricted | Medium |
| Directory Browsing Enabled | Server exposes folder structure | Medium |
| Missing Anti-Clickjacking Header | X-Frame-Options not set | Medium |

---

## Recommendations

### Immediate Actions
- Enable HTTPS across the website  
- Update outdated services (SSH, Apache)  
- Restrict SSH access to trusted IP addresses  

### Short-Term Improvements
- Close or secure unnecessary open ports  
- Configure security headers (CSP, X-Frame-Options, HSTS)  
- Disable directory browsing  
- Restrict cross-domain access  

### Long-Term Strategy
- Perform regular vulnerability assessments  
- Establish patch management processes  
- Implement continuous monitoring and logging  

---

## Evidence
All evidence is stored in the `evidence/` folder:

| File | Description |
|------|------------|
| `nmap.png` | Nmap scan output screenshot |
| `developer-tools.png` | Browser DevTools header inspection screenshot |
| `owasp-scan.png` | OWASP ZAP passive scan findings screenshot |
| `nmap-full-scan.png` | complete attack surface screenshot |
| `scanme-page.png` | vulnerable live website screenshot |


---

## Report
The **full vulnerability assessment report** is included in the `report/` folder:

- `report/vulnerability_report.pdf`  

It includes **all findings, risk levels, and remediation steps**,  

---

## Repository Structure

```bash
FUTURE_CS_01/
│
├── report/
│   └── vulnerabilityAssessmentReport.pdf
│
├── evidence/
│   ├── developer-tools.png
│   ├── nmap-full-scan.png
│   └── nmap.png
│   └── owasp-scan.png
│   └── scanme-page.png

│
├── scans/
│   └── final_scan.txt
│
└── README.md


