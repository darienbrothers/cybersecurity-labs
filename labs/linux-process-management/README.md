# Linux Process Management Lab

## Lab Overview

This lab explores how Linux systems manage running processes and how administrators and security professionals monitor and control system activity.

A **process** is any program currently running on a system. Each process is assigned a **Process ID (PID)** and can be inspected, filtered, or terminated using standard Linux utilities.

Understanding how to inspect and control processes is critical for:

• system administration
• malware detection
• incident response
• penetration testing

During this lab we practiced identifying active processes, searching for specific programs, launching background processes, terminating processes, and monitoring system activity in real time.

---

## Lab Environment

Operating System: Kali Linux
Hostname: kali-lab-01
Primary User: dbr0
Virtualization Platform: UTM (Apple Silicon)

---

## Commands Covered

The following commands were used throughout the lab.

| Command | Purpose                                            |
| ------- | -------------------------------------------------- |
| ps      | display running processes for the current terminal |
| ps -e   | display all running processes                      |
| ps -ef  | show full detailed process list                    |
| grep    | filter command output for specific text            |
| kill    | terminate a process using its PID                  |
| htop    | interactive process monitoring tool                |

---

## Exercise 1 — Viewing Active Processes

The `ps` command displays currently running processes.

Example command:

```
ps
```

Example output:

```
PID TTY          TIME CMD
2431 pts/0    00:00:00 bash
2450 pts/0    00:00:00 ps
```

This command only shows processes running in the current terminal session.

To view **all processes on the system**, the following command was used:

```
ps -e
```

Screenshot:

```
screenshots/process-listing.png
```

---

## Exercise 2 — Searching for Processes

Processes can be filtered using the `grep` utility.

Example command:

```
ps -ef | grep bash
```

Explanation:

• `ps -ef` displays all processes in full format
• `|` sends the output to another command
• `grep bash` filters results containing the word "bash"

Example output:

```
dbr0      2431   2400  0 pts/0    00:00:00 bash
dbr0      2550   2431  0 pts/0    00:00:00 grep bash
```

Screenshot:

```
screenshots/process-search-grep.png
```

This command is commonly used in security investigations to locate suspicious processes.

---

## Exercise 3 — Terminating a Process

A background process was created using the `sleep` command.

```
sleep 300 &
```

The ampersand (`&`) runs the command in the background.

The process was located using:

```
ps -ef | grep sleep
```

Example output:

```
dbr0   3125   2431  0 pts/0  00:00:00 sleep 300
```

The process was terminated using:

```
kill 3125
```

If a process refuses to terminate normally, a forced termination signal can be used:

```
kill -9 <PID>
```

Screenshot:

```
screenshots/kill-process-exercise.png
```

---

## Exercise 4 — Monitoring Processes with htop

The `htop` utility provides an interactive interface for monitoring system processes.

Command used:

```
htop
```

Features of the interface include:

• real-time CPU usage monitoring
• memory usage statistics
• process ownership and PID tracking
• interactive process termination

Common keyboard shortcuts:

| Key | Function         |
| --- | ---------------- |
| F3  | search processes |
| F4  | filter processes |
| F5  | tree view        |
| F9  | kill process     |
| F10 | exit             |

Screenshot:

```
screenshots/htop-process-monitor.png
```

---

## Security Relevance

Process monitoring is essential for detecting malicious activity on Linux systems.

Security analysts frequently inspect processes to identify:

• unauthorized remote shells
• crypto-mining malware
• reverse shell connections
• privilege escalation attempts
• suspicious background services

Commands such as `ps`, `grep`, and `kill` are commonly used during **incident response and forensic investigations**.

---

## Skills Demonstrated

This lab demonstrates the ability to:

• inspect running Linux processes
• filter process lists to locate specific programs
• terminate running processes using PID values
• monitor system resource usage
• use interactive monitoring tools

These skills are foundational for Linux system administration and cybersecurity operations.

---
