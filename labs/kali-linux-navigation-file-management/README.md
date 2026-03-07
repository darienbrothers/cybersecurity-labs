# Kali Linux Navigation & File Management Lab

## Lab Overview

This lab introduces the fundamental Linux commands used to navigate the filesystem and manage files inside Kali Linux.

These commands are essential for working with cybersecurity tools because most offensive and defensive security tooling operates within a Linux environment.

In this lab we will practice creating directories, creating files, moving files, copying files, reading file contents, and searching for text using common Linux commands.

---

## Lab Objectives

By completing this lab you will learn how to:

• Navigate the Linux filesystem
• Create and manage directories
• Create and modify files
• Move and rename files
• Copy files between directories
• View file contents
• Search file contents using grep

These skills form the foundation for working with security tools in Kali Linux.

---

## Lab Environment

Machine: Kali Linux Virtual Machine
Hypervisor: UTM
Shell: Bash Terminal

All commands in this lab are executed directly inside the Kali Linux terminal.

---

## Lab Workspace Setup

First we will create a workspace where all lab files will live.

Open the Kali terminal and run the following commands:

```
mkdir cyber-lab-practice
cd cyber-lab-practice
pwd
```

What this does:

• `mkdir` creates a new directory
• `cd` moves you into that directory
• `pwd` prints the current working directory

Screenshot checkpoint:

Take a screenshot showing the output of the `pwd` command inside the new directory.

Save it in:

```
screenshots/lab-workspace-created.png
```

---

## Exercise 1 – Create Files

Run the following commands:

```
touch notes.txt
touch tasks.txt
touch logs.txt
ls
```

Explanation:

• `touch` creates empty files
• `ls` lists files in the directory

Screenshot checkpoint:

Capture the output of `ls` showing the three files.

Save screenshot as:

```
screenshots/files-created.png
```

---

## Exercise 2 – Add Content to Files

Add text to the notes file.

Run:

```
echo "This is my first cybersecurity lab." > notes.txt
echo "Learning Linux navigation and file management." >> notes.txt
```

Explanation:

• `>` writes text to a file
• `>>` appends text to a file

Verify the contents:

```
cat notes.txt
```

Screenshot checkpoint:

Capture the output of `cat notes.txt`.

Save screenshot as:

```
screenshots/notes-file-content.png
```

---

## Exercise 3 – Copy a File

Run:

```
cp notes.txt backup-notes.txt
ls
```

Explanation:

• `cp` copies a file

You should now see:

```
notes.txt
backup-notes.txt
tasks.txt
logs.txt
```

Screenshot checkpoint:

Save screenshot as:

```
screenshots/file-copy.png
```

---

## Exercise 4 – Move and Rename a File

Rename the tasks file.

Run:

```
mv tasks.txt todo.txt
ls
```

Explanation:

• `mv` moves or renames files

Screenshot checkpoint:

Save screenshot as:

```
screenshots/file-rename.png
```

---

## Exercise 5 – Search for Text Using Grep

Search inside the notes file.

Run:

```
grep cybersecurity notes.txt
```

Explanation:

`grep` searches files for specific text patterns.

Screenshot checkpoint:

Save screenshot as:

```
screenshots/grep-search.png
```

---

## Exercise 6 – Remove a File

Run:

```
rm logs.txt
ls
```

Explanation:

• `rm` removes a file

Screenshot checkpoint:

Save screenshot as:

```
screenshots/file-removed.png
```

---

## Commands Practiced

The following Linux commands were practiced in this lab:

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
grep
```

---

## Lessons Learned

This lab introduced the core Linux commands used for filesystem navigation and file management in Kali Linux.

Understanding these commands is critical because cybersecurity tools often require navigating directories, manipulating files, reading logs, and searching for specific patterns inside large datasets.

These skills form the operational foundation required before moving into more advanced topics such as network scanning, exploitation frameworks, and log analysis.
