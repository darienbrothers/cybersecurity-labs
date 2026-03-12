# Cryptography & Hashing Lab

## Objective

The goal of this lab is to understand how cryptographic hashing works and how hashes can be generated and analyzed using Linux command-line tools.

This lab demonstrates how hashing is used to protect data integrity and how attackers may attempt to crack password hashes.

---

## Environment

Attacker Machine  
Kali Linux  
Hostname: kali-lab-01  
User: dbr0  

Lab Platform  
UTM Virtualization  
Metasploitable VM available for later labs

---

## Tools Used

- md5sum
- sha512sum
- sha384sum
- openssl
- hashcat

---

## Lab Setup

This lab creates sample files and generates cryptographic hashes for analysis.

---

## Methodology

The lab follows these steps:

1. Create a workspace for hashing exercises
2. Generate sample files
3. Create hashes using multiple algorithms
4. Compare hash outputs
5. Generate salted hashes using OpenSSL
6. Prepare hashes for password cracking

---

## Evidence

Screenshots are stored in:
screenshots/


Artifacts such as hash files are stored in:
artifacts/

---

## Hash Generation

Three sample files were created in the hashing lab environment.
file1.txt
file2.txt
password.txt

Hashes were generated using multiple algorithms.

### MD5 Hash
md5sum file1.txt

### SHA512 Hash
sha512sum file1.txt

Also used md5sum * and sha512sum * to hash all the files.


The results were saved to artifact files for analysis.

Artifacts stored in:
artifacts/md5-hashes.txt
artifacts/sha512-hashes.txt

Screenshots documenting the hashing process are available in the screenshots directory.

---

## Next Steps

The next lab will demonstrate password cracking techniques using Hashcat.
