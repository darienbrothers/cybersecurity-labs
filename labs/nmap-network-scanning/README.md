# Nmap Network Scanning

## Lab Overview

This lab introduces network reconnaissance using **Nmap**, a widely used network scanning and discovery tool.

The goal of this lab is to:

- Verify network connectivity between attacker and target machines
- Discover active hosts on the network
- Identify open ports on a target system
- Understand how Nmap uses TCP behavior to determine port states

All activities are performed inside a controlled virtual lab environment.

---

## Lab Environment

### Attacker Machine

Kali Linux  
User: `dbr0`  
IP Address: `10.0.2.x`

### Target Machine

Metasploitable2  
IP Address: `10.0.2.x`

Both machines run inside a virtual environment using **UTM** and must be connected to the **same subnet** before scanning can begin.

---

## Network Troubleshooting

Before running Nmap scans, it is important to verify that both machines can communicate on the network.

During initial setup the machines were assigned IP addresses on **different subnets**, which prevented connectivity.

Example issue encountered:

**Kali**
192.168.x.x

**Metasploitable**
10.0.2.x

Because the machines were on different networks, the attacker machine could not reach the target.

The issue was resolved by ensuring both virtual machines were configured on the **same virtual network** inside UTM.

After correcting the configuration, both machines received addresses within the same subnet:10.0.2.x


Once both systems were reachable on the same network, scanning could proceed.

---

## Step 1 — Verify Network Connectivity

Before performing reconnaissance, verify that the attacker machine can reach the target.

Run the following command from Kali:
ping <target-ip>

Example:
ping 10.0.2.x


If the network is configured correctly, the attacker machine should receive responses from the target.

Successful communication confirms that the machines can interact at the network layer.

---

## Step 2 — Confirm Local Network Configuration

To view the IP address assigned to the Kali machine, run:
ip a


This command displays network interfaces and assigned IP addresses.

Verify that the system is operating within the expected subnet.

---

## Step 3 — Host Discovery

Host discovery identifies active systems on a network before performing port scans.

Run: nmap -sn 10.0.2.0/24


Explanation:

- `-sn` disables port scanning
- Performs host discovery only
- Uses ICMP echo requests and ARP requests

The scan should identify the **Metasploitable target** as an active host.

---

## Step 4 — Basic Port Scan

Once a host has been identified, perform a basic scan:
nmap <target-ip>


Example:
nmap 10.0.2.x


This scan checks the **most common ports** to determine which services are accessible.

---

## Step 5 — SYN Scan (Stealth Scan)

Run: sudo nmap -sS <target-ip>


Explanation:

- Sends TCP SYN packets
- Does not complete a full TCP connection
- Often referred to as a **stealth scan**

Possible responses:

| Response | Meaning |
|--------|--------|
| SYN/ACK | Port is open |
| RST | Port is closed |
| No response | Port is filtered |

This behavior is based on the **TCP three-way handshake**, defined in:

RFC 793 — Transmission Control Protocol  
https://datatracker.ietf.org/doc/html/rfc793

---

## Screenshots

Screenshots for this lab are stored in: labs/nmap-network-scanning/screenshots


Examples include:

- Network interface verification
- Successful ping test
- Host discovery results
- Nmap port scanning output

---

## Next Lab

The next lab will focus on **service enumeration**, using Nmap to identify versions of services running on discovered ports.

Example command:
nmap -sV <target-ip>


Service enumeration helps identify potential vulnerabilities within exposed services.

