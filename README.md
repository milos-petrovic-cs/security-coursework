# Vulnerability Triage Challenge
Course: ICST 454 - Cybersecurity | Evangel University
Module: 5, Lecture 1 | March 24, 2026

## Scenario
Junior security analyst at Ridgeline Regional Medical Center, 200-bed HIPAA-covered community hospital. The IT team completed a quarterly Nessus scan and 2hr maintenance window opens tonight. Task: identify the 3 findings to fix immediately and rank the rest for future windows.

## Skills Demonstrated
-CVE analysis and CVSS scoring
-Risk prioritization (CVSS + exposure + business impact)
-HIPAA Security Rule context
-Compensating controls
-Vulnerability triage methodology

## Top 3 Immediate Fixes
| Finding | CVE | Vulnerability | CVSS | Reasons |
| --------- | ----- | ------------- | ------ | 
| A | CVE-2021-44228 | Log4Shell - EHR Server | 10.0 | Active exploits, internal PHI exposure |
| E | CVE-2022-22965 | Spring4Shell - Patient Portal | 9.8 | Internet-facing RCE |
| G | CVE-2019-11510 | Pulse Secure VPN | 10.0 | Internet-facing, ransomware entry point |

## Remaining 5 - Prioritized 
| Priority | Finding | Vulnerability | Timeline |
| --------- | ----- | ------------- | ------ | 
| #4 | C | PrintNightmare (x12 workstations) | Urgent |
| #5 | F | SMB Signing Disabled (x15 hosts) | Urgent |
| #6 | D | SSL Self-Signed Certificate | Planned |
| #7 | B | OpenSSH Username Enumeration | Planned |
| #8 | H | TLS 1.0/1.1 Enabled | Scheduled |

## Compensating Control - Finding C (PrintNightmare)
Disable the Windows Print Spooler service on all 12 nurse workstations via Group Policy ('Stop-Service -Name Spooler - Force'). Eliminates attack surface without patching. Microsoft's own recommended mitigation.

## Tools & Frameworks
-Nessus (simulated scan output)
-CVSS v3 scoring
-HIPAA Security Rule
-MITRE ATT&CK
