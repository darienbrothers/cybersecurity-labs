# Kali Linux Navigation & File Management Lab

## Objective

The goal of this lab is to learn how to navigate the Linux filesystem and manage files using the command line.

These skills are essential in cybersecurity because most security tools operate in a Linux terminal environment.

Skills demonstrated:

• navigating the Linux filesystem  
• creating directories and files  
• copying and moving files  
• inspecting file contents  
• searching logs using grep  
• organizing investigation data

These foundational skills are required before using advanced security tools.

---

## Environment

Operating System: Kali Linux  
Hostname: kali-lab-01  
Primary User: dbr0  
Virtualization Platform: UTM (Apple Silicon)

Note:

Initial exercises were completed using the default Kali user (`kali`).  
Later labs use a dedicated lab user (`dbr0`) for security practice.

---

## Tools Used

The following Linux commands were used during this lab.

| Tool | Purpose |
|-----|--------|
| pwd | display current working directory |
| ls | list directory contents |
| cd | change directory |
| mkdir | create directories |
| touch | create empty files |
| cp | copy files |
| mv | move files |
| rm | delete files |
| cat | display file contents |
| head | view beginning of file |
| tail | view end of file |
| grep | search text patterns in files |

---

## Commands Executed

### Workspace Setup

A workspace was created to store investigation files.

mkdir cyber-lab-practice
cd cyber-lab-practice
pwd

Purpose:

• `mkdir` creates a directory  
• `cd` changes the current directory  
• `pwd` confirms the working path  

---

### Creating Files

touch access.log
touch credentials.txt
touch notes.txt
ls

Purpose:

• `touch` creates empty files  
• `ls` lists files in the current directory  

Files created:

access.log
credentials.txt
notes.txt

---

### Organizing Files

Directories were created to organize investigation data.

mkdir logs credentials notes
mv access.log logs/
mv credentials.txt credentials/
mv notes.txt notes/

A backup of the log file was created:

cp logs/access.log logs/access_backup.log

Resulting structure:

logs/
credentials/
notes/

---

### Log Analysis

Example commands used to inspect log files:

head logs/access.log
tail logs/access.log
grep -i login logs/access.log
grep Failed logs/access.log

Purpose:

• `head` displays the first lines of a file  
• `tail` displays the last lines of a file  
• `grep` searches for text patterns within files  

This simulated searching logs for suspicious login activity.

---

## Findings

The lab demonstrated how Linux command-line tools can be used to navigate directories, organize files, and analyze log data.

Key observations:

• Linux systems organize data in hierarchical directories  
• Files can be created and moved quickly using command-line tools  
• Investigation data should be structured into logical directories  
• Logs can be analyzed efficiently using text-processing tools such as `grep`

---

## Screenshots

Evidence of commands and results are located in:
screenshots/

Examples include:

• lab-workspace-created.png  
• file-creation-and-grep.png  
• file-organization-and-copy.png  
• log-analysis-and-cleanup.png  

---

## Lessons Learned

Linux command-line navigation is a fundamental skill in cybersecurity operations.

Security professionals regularly use command-line tools to:

• analyze system logs  
• organize investigation data  
• search for indicators of compromise  
• inspect system activity

Understanding these commands is necessary before progressing to more advanced tasks such as network scanning, exploitation frameworks, and forensic analysis.

---

## Next Lab

The next lab focuses on **Linux Permissions and User Management**.

This lab introduces how Linux controls access to files and system resources through:

• user accounts  
• groups  
• file ownership  
• permission levels (read, write, execute)

Understanding Linux permissions is essential for system administration and security because improper permissions can lead to privilege escalation or unauthorized access.
