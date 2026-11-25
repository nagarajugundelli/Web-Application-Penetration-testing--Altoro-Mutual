# Web-Application-Penetration-testing--Altoro-Mutual
Manual web application security assessment and Reflected XSS PoC on Altoro mutual (authorized lab)

## Project Overview
This repository documents a manual web application vulnerability assessment conducted against **Altoro Mutual (`testfire.net`)**, a deliberately vulnerable banking application designed for authorized security testing and training.

The objective of this assessment was to manually inspect HTTP traffic, identify input validation and access-control weaknesses aligned with the OWASP Top 10, validate findings using Burp Suite, and document actionable remediation steps.

## Scope & Environment
- **Target:** Altoro Mutual (`http://testfire.net` — Authorized Lab)
- **Testing Type:** Manual Web Application Security Assessment (Black/Grey-Box)
- **Tools Used:**
  - Kali Linux
  - Burp Suite Community Edition (Proxy, Repeater, HTTP History)
  - Browser Developer Tools

## Methodology
- **Reconnaissance & Mapping:** Explored application pages, authentication flows, and user input parameters while capturing traffic through Burp Proxy.
- **Input Reflection & Injection Analysis:** Tested search and form parameters using harmless markers to trace how user input is handled and rendered in HTTP responses.
- **Manual Verification:** Replayed modified requests in Burp Repeater to eliminate false positives and confirm exploitability.
- **Reporting & Remediation:** Documented confirmed issues with reproduction steps, Proof of Concept (PoC) evidence, impact analysis, and defensive fixes.

## Findings Summary

| ID | Vulnerability | Affected Area | Severity | Report |
| :--- | :--- | :--- | :--- | :--- |
| 01 | Reflected Cross-Site Scripting (XSS) | Search / Input Parameter | Medium | [View Report](findings/xss-finding.md) |

## Repository Structure
- `README.md` — Assessment overview, scope, methodology, and findings summary.
- `findings/` — Detailed vulnerability report (`findings/xss-finding.md`).
- `screenshots/` — Proof of Concept (PoC) screenshots from manual verification.

## Disclaimer
All testing documented in this repository was conducted strictly against an authorized practice lab (`testfire.net`) for educational and portfolio purposes.
