# Day 02: Network Service Auditing & Fingerprinting 🛰️

**Date:** April 1, 2026
**Target System:** Metasploitable 2 (Internal Lab)
**IP Address:** 10.0.2.2
**Objective:** Execute high-fidelity service enumeration to identify software versions and quantify network attack surface.

---

## 🛠️ Execution & Discovery
I performed an advanced network audit using `nmap` to identify active services and their corresponding version numbers. Capturing version data is a critical step in the Vulnerability Management lifecycle to move from simple port discovery to actionable threat intelligence.

- **Command:** `sudo nmap -sV -sC -O -oX AoraSec_Test_Data.xml 10.0.2.2`
- **Output:** Structured telemetry captured in XML format for automated data analysis.

---

## 📊 Technical Findings
The audit identified several high-risk services with well-documented vulnerabilities. By identifying specific versions, we can pinpoint exact CVEs (Common Vulnerabilities and Exposures).

| Port | Service | Version | Risk Profile |
| :--- | :--- | :--- | :--- |
| 21 | FTP | vsftpd 2.3.4 | **Critical**: Backdoor vulnerability |
| 6667 | IRC | UnrealIRCd | **High**: Remote Code Execution (RCE) |
| 80 | HTTP | Apache 2.2.8 | **Medium**: Legacy version; Path Traversal |
| 5432 | PostgreSQL | 8.3.0 | **Medium**: Database Exposure Risk |

---

## 💰 GRC & Financial Risk Logic
As a Vulnerability Analyst, I evaluated the financial risk of this asset based on a hypothetical **Asset Value (AV) of $100,000**:

- **Exposure Factor (EF):** 0.25 (Estimated 25% loss of integrity/availability upon exploit).
- **Single Loss Expectancy (SLE):** $25,000
- **Annual Rate of Occurrence (ARO):** 0.5 (Estimated event frequency of once every two years).
- **Annual Loss Expectancy (ALE):** $12,500

---

## 💡 Key Takeaways
- **Precision Matters:** Utilizing the `-sV` and `-sC` flags revealed critical version data that a standard ping sweep would have missed.
- **Data Portability:** The XML output (`-oX`) allows for this data to be integrated into broader security workflows and reporting engines.