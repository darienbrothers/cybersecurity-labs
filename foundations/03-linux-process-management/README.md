# Linux Process Management Lab

## Objective

The goal of this lab is to understand how Linux manages running processes and how administrators and security professionals monitor and control system activity.

A **process** is any program currently running on a system. Each process is assigned a **Process ID (PID)** and can be inspected, filtered, or terminated using standard Linux utilities.

Skills demonstrated:

• Viewing active system processes  
• Filtering processes to locate specific programs  
• Running background processes  
• Terminating processes using PID  
• Monitoring system activity in real time

These skills are important for system administration, malware detection, incident response, and penetration testing.

---

## Environment

Operating System: Kali Linux  
Hostname: kali-lab-01  
Primary User: dbr0  
Virtualization Platform: UTM (Apple Silicon)

---

## Tools Used

The following Linux utilities were used during this lab:

| Tool | Purpose |
|-----|--------|
| ps | Displays running processes |
| grep | Filters command output |
| kill | Terminates processes |
| htop | Interactive system monitoring tool |
| sleep | Creates test processes |

---

## Commands Executed

### Viewing Running Processes

ps
Displays processes running in the current terminal session.

ps -e
Displays **all processes running on the system**.

ps -ef
Shows processes in full detailed format including parent process IDs and ownership.

---

### Searching for Processes
ps -ef | grep bash

Explanation:

• `ps -ef` lists all running processes  
• `|` passes output to another command  
• `grep bash` filters results containing the word "bash"

This method is commonly used to locate specific processes during system monitoring or security investigations.

---

### Creating a Background Process

A background process was created using: 
sleep 300 &

Explanation:

• `sleep 300` pauses execution for 300 seconds  
• `&` runs the command in the background

The process was located using:
ps -ef | grep sleep

---

### Terminating a Process

Once the PID was identified, the process was terminated using:
kill -15 <PID>

If the process does not terminate normally, a forced termination can be used:
kill -9 <PID>

This sends a **SIGKILL signal**, immediately stopping the process.

---

### Monitoring Processes with htop
`htop` provides a real-time interactive interface showing:

• CPU utilization  
• memory usage  
• running processes  
• process hierarchy

Common keyboard shortcuts:

| Key | Function |
|----|----------|
| F3 | Search |
| F4 | Filter |
| F5 | Tree view |
| F9 | Kill process |
| F10 | Exit |

---

## Findings

The lab demonstrated how Linux systems manage processes and how administrators can monitor and control running programs.

Key observations:

• Each running program receives a **unique PID**  
• The `ps` command allows administrators to inspect running processes  
• The `grep` utility enables filtering large process lists  
• Background processes can be created using `&`  
• Processes can be terminated using the `kill` command  
• The `htop` utility provides real-time monitoring of system activity

---

## Screenshots

Screenshots demonstrating the commands and results are stored in:
screenshots/

Example screenshots include:

• process-listing.png  
• process-search-grep.png  
• kill-process-exercise.png  
• htop-process-monitor.png  

---

## Lessons Learned

Understanding how to monitor and control Linux processes is essential for system administration and cybersecurity operations.

Security professionals frequently inspect running processes to detect:

• malicious background services  
• unauthorized remote shells  
• crypto-mining malware  
• reverse shell connections  
• suspicious system activity

Commands such as `ps`, `grep`, `kill`, and `htop` are commonly used during **incident response and forensic investigations**.
