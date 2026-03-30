# Kali Linux Navigation & File Management Lab

## Objective
The goal of this lab is to master Linux filesystem navigation and file management via the command line. These foundational skills are essential for security operations, as most industry-standard tools and servers operate in a terminal environment.

**Skills demonstrated:**
* Navigating the Linux filesystem and hierarchical structures.
* Creating, moving, and organizing investigation data.
* Inspecting file contents and searching logs using `grep`.
* **Forensic Discovery:** Identifying hidden adversary artifacts.
* **System Hardening:** Remediating insecure file permissions (Least Privilege).

---

## Environment
* **Operating System:** Kali Linux
* **Hostname:** kali-lab-01
* **Primary User:** dbr0
* **Virtualization Platform:** UTM (Apple Silicon)

---

## Tools Used
| Tool | Purpose |
|:---|:---|
| **pwd** | Display current working directory |
| **ls** | List directory contents (used with `-la` for audits) |
| **cd** | Change directory |
| **mkdir** | Create directories |
| **touch** | Create empty files |
| **cp / mv** | Copy or Move files |
| **grep** | Search text patterns in files |
| **find** | Forensic search tool to locate files by name/pattern |
| **chmod** | Change file permissions for security hardening |

---

## Commands Executed

### 1. Workspace Setup & Log Analysis
A structured workspace was created to organize investigation data, simulating the preparation required for a security audit.
* Created directories for `logs/`, `credentials/`, and `notes/`.
* Simulated log analysis using `grep` to identify failed login attempts within `access.log`.

### 2. Security Workflow: Forensic Discovery
This task simulates an audit where an analyst must locate "hidden" files an adversary might have buried in the system to maintain persistence.

**The Discovery:**
Using the `find` command, a recursive search was conducted for any files containing "creds" in the name.

```bash
find . -name "*creds*"
```
Result: Uncovered a hidden file at ./internal/backups/temp/syslog/.db_creds.txt. The leading dot (.) ensures the file remains hidden from standard ls views, a common tactic for masking sensitive data.

### 3. Security Workflow: System Hardening
Upon discovery, an audit of the file metadata revealed a critical permission vulnerability.

The Audit:
Running ls -la showed the file was "World Readable" (-rw-rw-r--). This configuration violates security standards by allowing any user on the system to read the credentials.

The Remediation:
Applied the Principle of Least Privilege to restrict access solely to the file owner.

Bash
chmod 600 internal/backups/temp/syslog/.db_creds.txt
Result: Successfully hardened the file to -rw-------, effectively plugging the data exposure hole.

### Technical Evidence
Evidence of the lab progression and security remediations are located in the screenshots/ directory:

01_lab_workspace_created.png

02_file_creation_and_grep.png

03_file_organization_and_copy.png

04_log_analysis_and_cleanup.png

05_forensic_discovery_hidden_file.png (Uncovering the hidden credential file)

06_security_hardening_permissions_fix.png (Restricting file access via chmod 600)

### Lessons Learned & QA Perspective
This lab highlights the direct overlap between Quality Assurance and Security Engineering. In software QA, the focus is on identifying and documenting code bugs; in Security, the focus is on identifying configuration bugs.

The process followed here—Verification (finding the file), Documentation (logging the risk), and Remediation (applying the fix)—mirrors the standard QA lifecycle, ensuring the infrastructure is as secure and reliable as the software it runs.

### Next Lab
The next lab moves into Network Reconnaissance and Service Enumeration, focusing on identifying open ports and vulnerable services using Nmap.
