# Nmap Network Scanning Lab

## Objective

The goal of this lab is to learn how to perform network reconnaissance using Nmap.

Nmap is used to discover hosts, identify open ports, detect running services, and fingerprint operating systems on a network.

Skills demonstrated:

• host discovery  
• TCP port scanning  
• SYN stealth scanning  
• UDP scanning  
• service version detection  
• OS fingerprinting  
• banner grabbing  

Source:  
https://nmap.org/book/man.html

---

## Environment

Attacker Machine  
Kali Linux  
Hostname: kali-lab-01  
User: dbr0  

Target Machine  
Metasploitable2  

Network Type  
Internal NAT Lab Network  

Example Target IP  
10.0.2.X (masked)

---

## Tools Used

• Nmap  
• Netcat  
• arp-scan  
• netdiscover  

---

## Commands Executed

### Host Discovery

To identify active hosts on the lab network, a ping scan was performed.

Command executed:

sudo nmap -sn 10.0.2.0/24

Explanation:

- `-sn` performs host discovery without performing a port scan
- `/24` scans the entire subnet (256 possible IP addresses)

Result:

Three active hosts were discovered on the network.

10.0.2.1 – NAT gateway  
10.0.2.2 – Metasploitable2 target system  
10.0.2.3 – Kali Linux attacker machine  

Screenshot:

![Host Discovery](screenshots/01_host_discovery_ping_scan.png)

Source:  
https://nmap.org/book/host-discovery.html

---

### Basic Port Scan

After identifying the target host, a TCP connect scan was performed to identify open ports.

Command executed:

sudo nmap -sT 10.0.2.2

Explanation:

- `-sT` performs a TCP connect scan
- This scan completes a full TCP handshake to determine if a port is open

Result:

Multiple open services were identified on the Metasploitable2 system including FTP, SSH, Telnet, SMTP, HTTP, SMB, MySQL, PostgreSQL, and VNC.

Example open ports identified:

21/tcp – ftp  
22/tcp – ssh  
23/tcp – telnet  
25/tcp – smtp  
80/tcp – http  
139/tcp – netbios-ssn  
445/tcp – microsoft-ds  
3306/tcp – mysql  
5432/tcp – postgresql  

Screenshot:

![Basic Port Scan](screenshots/02_basic_port_scan.png)

Source:  
https://nmap.org/book/man-port-scanning-techniques.html

---

## Findings

This section will summarize the results discovered during the scans including open ports, services running on the target system, and operating system detection.

---

## Screenshots

Evidence of commands and scan results are stored in:

screenshots/

---

## Lessons Learned

This section will describe the reconnaissance techniques demonstrated in the lab and explain how Nmap is used during penetration testing engagements.
