# Linux Permissions & User Management Lab

## Objective

The goal of this lab is to understand how Linux controls access to files and system resources through permissions, ownership, and user management.

Linux systems use a permission model that determines which users can read, write, or execute files. Proper permission management is critical for maintaining system security and preventing unauthorized access.

Skills demonstrated:

• creating and managing user accounts  
• inspecting file permissions  
• modifying file permissions with `chmod`  
• changing file ownership with `chown`  
• understanding numeric permission values (such as 744 and 600)

These concepts are fundamental for system administration, privilege management, and security operations.

---

## Environment

Operating System: Kali Linux  
Hostname: kali-lab-01  
Primary User: dbr0  
Virtualization Platform: UTM (Apple Silicon)

---

## Tools Used

The following Linux utilities were used during this lab.

| Tool | Purpose |
|-----|--------|
| useradd | create new user accounts |
| passwd | set or change user passwords |
| id | display user and group information |
| groups | list group memberships |
| ls -l | view file permissions and ownership |
| chmod | change file permissions |
| chown | change file ownership |
| su | switch user accounts |

---

## Commands Executed

### Creating a New User

A new user account was created for lab practice.
sudo useradd testuser

A password was assigned to the new user.
sudo passwd testuser

User information was verified using:
id testuser

Purpose:

• `useradd` creates a new user account  
• `passwd` assigns a password  
• `id` displays user and group identifiers

---

### Inspecting File Permissions

File permissions were inspected using:
ls -l

Example output:
-rw-r–r– 1 dbr0 dbr0 0 Jun 10 example.txt

Permission breakdown:

| Section | Meaning |
|------|------|
| rw- | owner permissions |
| r-- | group permissions |
| r-- | others permissions |

This shows that the owner can read and write the file, while group and other users can only read it.

---

### Changing File Permissions

Permissions were modified using the `chmod` command.

Example:
chmod 744 example.txt

Numeric permissions represent:

| Value | Permission |
|------|-----------|
| 7 | read, write, execute |
| 4 | read only |
| 0 | no permission |

Another example:
chmod 600 credentials.txt

This restricts access so that **only the file owner can read or write the file**.

---

### Changing File Ownership

Ownership of a file was modified using:
sudo chown testuser example.txt

Purpose:

• `chown` changes the owner of a file or directory  
• used when transferring control of files between users

Ownership changes can be verified using:
ls -l

---

## Findings

The lab demonstrated how Linux systems enforce access control using file permissions and ownership.

Key observations:

• every file has an owner and group assignment  
• permissions determine who can read, write, or execute files  
• numeric permission values simplify permission management  
• improper permissions can expose sensitive data to unauthorized users

Managing file permissions correctly is essential for maintaining secure systems.

---

## Screenshots

Screenshots demonstrating commands and permission changes are stored in:
screenshots/

Examples include:

• user-creation.png  
• permission-view.png  
• chmod-example.png  
• chown-example.png  

---

## Lessons Learned

Linux permission management is a core security control within the operating system.

Security professionals must understand how permissions work in order to:

• prevent unauthorized access to sensitive files  
• detect privilege escalation attempts  
• secure system configuration files  
• manage user access to system resources

Misconfigured permissions are a common cause of security vulnerabilities in Linux systems.

---

## Next Lab

The next lab explores **Linux Process Management**.

This lab demonstrates how to monitor running processes, identify suspicious activity, and terminate processes using tools such as:

• `ps`  
• `grep`  
• `kill`  
• `htop`

Understanding process management is essential for system monitoring, incident response, and detecting malicious activity on Linux systems.

