# Kali Linux Navigation & File Management Lab

## Lab Overview

This lab introduces fundamental Linux filesystem navigation and file management commands inside Kali Linux. These commands are essential when working in cybersecurity because most security tools operate in a Linux terminal environment.

The purpose of this lab is to develop confidence using the command line to create files, organize directories, inspect file contents, and search logs for suspicious activity.

---

## Lab Objectives

By completing this lab you should be able to:

• Navigate the Linux filesystem using the terminal
• Create directories and files
• Move and copy files between directories
• Inspect file contents using command-line tools
• Search logs for specific patterns using `grep`
• Organize investigation data into structured directories

These skills form the operational foundation required before working with advanced security tools.

---

## Lab Environment

Machine: Kali Linux Virtual Machine
Hypervisor: UTM
Shell: Bash Terminal
Hostname: kali-lab-01

All commands were executed directly in the Kali Linux terminal.

---

## Lab Workspace Setup

First we created a workspace to store all files used in the lab.

Commands used:

```
mkdir cyber-lab-practice
cd cyber-lab-practice
pwd
```

Purpose:

• `mkdir` creates a directory
• `cd` changes the current directory
• `pwd` confirms the current working path

Screenshot evidence:

```
screenshots/lab-workspace-created.png
```

---

## Exercise 1 — Creating Files

Commands used:

```
touch access.log
touch credentials.txt
touch notes.txt
ls
```

Purpose:

• `touch` creates empty files
• `ls` lists files in the directory

Files created:

```
access.log
credentials.txt
notes.txt
```

Dummy log and credential content was added to simulate investigation data.

Screenshot evidence:

```
screenshots/file-creation-and-grep.png
```

---

## Exercise 2 — Organizing Files

Commands used:

```
mkdir logs credentials notes
mv access.log logs/
mv credentials.txt credentials/
mv notes.txt notes/
ls
```

Purpose:

• `mkdir` creates directories
• `mv` moves files between directories

Directory structure created:

```
logs/
credentials/
notes/
```

A backup copy of the log file was also created:

```
cp logs/access.log logs/access_backup.log
```

Screenshot evidence:

```
screenshots/file-organization-and-copy.png
```

---

## Exercise 3 — Log Analysis

Commands used:

```
head logs/access.log
tail logs/access.log
grep -i login logs/access.log
grep Failed logs/access.log
```

Purpose:

• `head` displays the first lines of a file
• `tail` displays the last lines of a file
• `grep` searches for specific text patterns inside files

This exercise simulated identifying suspicious login activity inside a log file.

Screenshot evidence:

```
screenshots/log-analysis-and-cleanup.png
```

---

## Commands Practiced

```
pwd
ls
cd
mkdir
touch
echo
cat
cp
mv
rm
head
tail
grep
```

---

## Lessons Learned

This lab demonstrated how Linux command-line tools are used to manage files and analyze data within a cybersecurity environment.

Key takeaways:

• The Linux terminal is the primary interface for most cybersecurity tools.
• Files and directories must be organized properly during investigations.
• Logs can be inspected quickly using tools such as `head`, `tail`, and `grep`.
• Searching logs for suspicious patterns is a common task in both offensive security and incident response.

Understanding these foundational commands is necessary before progressing to more advanced tasks such as network scanning, exploitation frameworks, and log analysis.

---

## Next Lab

The next lab will introduce **network reconnaissance** using the tool:

Nmap

This lab will teach how attackers discover hosts, open ports, and services running on a network.
