# Cybersecurity Lab Portfolio

This repository documents my hands-on cybersecurity training as I transition from QA engineering into offensive security.

⚠️ All labs are conducted in a controlled personal environment for educational and defensive security purposes.

After earning my CompTIA Security+ certification on March 5, I began building a structured home lab using Kali Linux and vulnerable virtual machines to practice real security techniques.

All exercises are conducted in a controlled personal lab environment.

---

# Lab Environment

The labs in this repository are performed using a small isolated virtual network built with virtual machines.

Attacker machine: Kali Linux  
Target machine: Metasploitable2  

Both systems run inside a controlled virtual lab network.

---

## Lab Network Architecture

The cybersecurity labs in this repository are conducted using an isolated virtual lab environment.

```
Attacker Machine
Kali Linux (10.0.2.3)
User: dbr0

        │
        │ Internal NAT Lab Network
        │

Target Machine
Metasploitable2 (10.0.2.2)
Intentionally vulnerable virtual machine used for security testing
```

The Kali Linux machine performs reconnaissance, enumeration, and security testing against the Metasploitable target system within a controlled internal network.

---

# Lab Methodology

Each lab in this repository follows a structured workflow similar to real-world cybersecurity assessments.

The goal is not only to learn tools, but to practice a repeatable process for discovering and analyzing security issues.

## 1. Environment Setup

Prepare the testing environment and verify connectivity between systems.

Typical actions include:

* verifying IP addresses
* confirming network connectivity
* preparing investigation directories
* ensuring tools are installed and functioning

---

## 2. Reconnaissance

Gather information about the target system or environment.

Examples:

* identifying active hosts
* discovering open ports
* mapping network services
* identifying exposed applications

Tools often used:

* nmap
* ping
* traceroute
* netstat
* ss

---

## 3. Enumeration

Once services are discovered, additional information is collected about those services.

Examples:

* service version detection
* operating system identification
* identifying authentication mechanisms
* collecting banner information

This phase helps determine potential attack surfaces.

---

## 4. Analysis and Documentation

All findings are documented during the lab.

Each lab typically includes:

* commands executed
* screenshots of results
* scan artifacts or output files
* explanations of findings
* lessons learned

The goal is to build a clear record of the testing process.

---

## 5. Continuous Learning

After completing each lab, new techniques and concepts are reviewed and practiced in future exercises.

As new skills are learned, additional labs will be added to this repository.

---

# Lab Index

Each lab contains documentation, screenshots, and artifacts collected during testing.

| Lab | Topic | Description |
|----|----|----|
| [01 - Kali Linux Navigation & File Management](labs/01-kali-linux-navigation-file-management) | Linux Fundamentals | Learn Linux command line navigation, file creation, directory organization, and log inspection |
| [02 - Linux Permissions & User Management](labs/02-linux-permissions-user-management) | Linux Security Fundamentals | Understand Linux permission models, file ownership, user management, and access control |
| [03 - Linux Process Management](labs/03-linux-process-management) | System Monitoring | Monitor running processes, identify suspicious activity, and terminate processes |
| [04 - Nmap Network Scanning](labs/04-nmap-network-scanning) | Network Reconnaissance | Perform host discovery, port scanning, service detection, OS fingerprinting, and enumeration |

---

# Lab Roadmap

## Linux Fundamentals

Completed

* Linux Navigation & File Management
* Linux Permissions & Ownership
* Linux User and Group Management
* Process Monitoring and Control

Skills practiced:

* command line navigation
* file permissions (`chmod`)
* file ownership (`chown`)
* privilege groups
* process inspection and termination

---

## Network Reconnaissance

Completed

* Network Scanning with Nmap
* Host Discovery
* Port Scanning Techniques
* Service Enumeration

Tools:

* nmap
* netstat
* ss
* ping
* traceroute

---

## Password Security

Planned

* Password Hashing Concepts
* Dictionary Attacks
* Brute Force Attacks
* Password Cracking with Hashcat
* Password Cracking with John the Ripper

---

## Web Application Security

Planned

* Web Server Enumeration
* Directory Discovery
* OWASP Top 10 vulnerabilities
* Testing against intentionally vulnerable applications

Targets:

* DVWA
* OWASP Juice Shop
* Metasploitable Web Services

---

## Social Engineering & Phishing Simulation

Planned

* Phishing awareness simulation
* Email attack simulations in a controlled environment
* Social engineering attack methodology

Tools:

* GoPhish
* Social Engineering Toolkit

---

## Malware & Incident Response Basics

Planned

* Identifying suspicious processes
* Reverse shell analysis
* Basic malware behavior observation
* Log inspection and cleanup

---

## Mobile Security

Planned

* Android application inspection
* Emulator-based security testing
* Mobile permission analysis

---

## IoT & Embedded Security (Future)

Exploration topics:

* IoT device security concepts
* Automotive system attack surfaces
* CAN bus fundamentals

---

# Tools Used

* Kali Linux
* Nmap
* Metasploitable
* Hashcat
* John the Ripper
* OWASP Juice Shop
* GoPhish

---

# Goal

Develop practical offensive security skills through structured labs and document the learning process publicly.

This repository will continue to evolve as new labs are completed.

---

## Disclaimer

All labs and tools in this repository are performed **only in controlled environments** for educational purposes.

These projects are intended to demonstrate cybersecurity concepts and defensive awareness.
