# Nmap Network Scanning

## Objective

The goal of this lab is to learn how to perform network reconnaissance using Nmap.  
Nmap is used to discover hosts, identify open ports, detect running services, and fingerprint operating systems.

Skills demonstrated:

- Host discovery
- TCP port scanning
- SYN stealth scanning
- UDP scanning
- Service version detection
- OS fingerprinting
- Banner grabbing

Source:
https://nmap.org/book/man.html

---

## Lab Environment

Attacker Machine  
Kali Linux  
Hostname: kali-lab-01  
User: dbr0  

Target Machine  
Metasploitable2  

Network Type  
Internal NAT Lab Network  

Example Target IP  
10.0.2.X (masked for security)

---

## Tools Used

- Nmap
- Netcat
- arp-scan
- netdiscover

---

## Lab Steps

1. Host Discovery
2. Basic Port Scanning
3. TCP Connect Scan
4. SYN Stealth Scan
5. UDP Scan
6. Banner Grabbing
7. Service and OS Fingerprinting

---

## Evidence

Screenshots for each step are stored in: screenshots/

---

## Key Takeaways

- Nmap can discover hosts and services across a network
- Different scan types provide different levels of stealth and detail
- Service detection and OS fingerprinting provide valuable intelligence for penetration testing

Source:
https://nmap.org/book/man-port-scanning-techniques.html
