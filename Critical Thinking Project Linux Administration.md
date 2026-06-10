# Critical Thinking Project: Operating System Basics in DevOps Automation and Scaling

## Project Overview

This project introduces fundamental operating system concepts that support DevOps automation, security, and scalability. The lab focuses on evaluating operating systems for DevOps workloads, learning essential Linux command-line operations, and implementing user and permission management.

---

# Objectives

By completing this lab, you will:

- Compare Linux and Windows for DevOps automation
- Learn essential Linux command-line operations
- Manage Linux users and permissions
- Understand security best practices in a DevOps environment

---

# Prerequisites

Before starting, ensure you have:

- Ubuntu Linux VM or server
- Sudo privileges
- Terminal access
- GitHub account

---

# Task 1: Choose the Best OS for DevOps Automation

## Objective

Evaluate Linux and Windows for DevOps automation based on:

- Scripting capabilities
- Package management
- Container support
- Performance
- Security

---

## Linux vs Windows Comparison

| Feature | Linux | Windows |
|----------|---------|----------|
| Automation | Bash, Shell Scripts | PowerShell |
| Package Management | APT, YUM, DNF | Winget, Chocolatey |
| Container Support | Native Docker/Kubernetes Support | Docker Support Available |
| Performance | Lightweight | Higher Resource Usage |
| Cost | Free/Open Source | Licensing Required |
| Security | Strong Permission Model | Strong Enterprise Security |
| Cloud Adoption | Industry Standard | Less Common |

---

## Analysis

Linux is the dominant operating system in modern DevOps environments. It provides excellent automation capabilities through shell scripting, native container support, and efficient resource utilization.

Windows offers strong integration with Microsoft ecosystems and PowerShell automation but is generally less preferred for containerized cloud-native workloads.

---

## Recommendation

### Recommended Operating System: Linux

### Reasons

1. Native Docker and Kubernetes support
2. Powerful Bash scripting capabilities
3. Lower hardware requirements
4. Open-source ecosystem
5. Strong security model
6. Industry-standard for cloud platforms

---

## Verification

Run:

```bash
uname -a
```

### Screenshot

<img width="1238" height="118" alt="image" src="https://github.com/user-attachments/assets/1ed3e3ba-11fd-4f66-bbe2-3ba241fbd363" />

**Figure 1: Linux Operating System Verification**

---

# Task 2: Introduction to the Linux Command Line

## Objective

Learn and practice basic Linux commands used in daily DevOps operations.

---

# Command 1: ls

## Purpose

Lists files and directories.

## Syntax

```bash
ls
```

## Example

```bash
ls -l
```

## DevOps Use Case

Used to inspect deployment directories and verify files.

### Screenshot

Run:

```bash
ls -l
```

**Figure 2: Listing Files and Directories**

---

# Command 2: cd

## Purpose

Changes the current directory.

## Syntax

```bash
cd directory_name
```

## Example

```bash
cd /var/log
```

## DevOps Use Case

Used to navigate logs and configuration directories.

### Verification

```bash
cd /var/log
pwd
```

### Screenshot

<img width="1264" height="1432" alt="image" src="https://github.com/user-attachments/assets/dec08831-dc24-466e-bcd2-5567102c98c2" />

<img width="1224" height="258" alt="image" src="https://github.com/user-attachments/assets/d0564a65-2294-4fce-9c37-e8beca74ad6a" />

**Figure 3: Navigating Directories**

---

# Command 3: mkdir

## Purpose

Creates a new directory.

## Syntax

```bash
mkdir directory_name
```

## Example

```bash
mkdir devops_project
```

## DevOps Use Case

Used to create project, backup, and deployment directories.

### Verification

```bash
mkdir devops_project
ls
```

### Screenshot

**Figure 4: Creating a Directory**

---

# Command 4: cat

## Purpose

Displays file contents.

## Syntax

```bash
cat filename
```

## Example

```bash
cat config.txt
```

## DevOps Use Case

Used to inspect configuration files and logs.

### Verification

```bash
echo "DevOps Configuration File" > config.txt
cat config.txt
```

### Screenshot

**Figure 5: Viewing File Contents**

---

# Command 5: rm

## Purpose

Removes files and directories.

## Syntax

```bash
rm filename
```

## Example

```bash
rm config.txt
```

## DevOps Use Case

Used to clean temporary files and old deployments.

### Verification

```bash
rm config.txt
ls
```

### Screenshot

<img width="792" height="160" alt="image" src="https://github.com/user-attachments/assets/fbee5e1b-74df-49d1-af32-3aef182c6c49" />

<img width="1220" height="302" alt="image" src="https://github.com/user-attachments/assets/e228e409-7706-4b10-9962-0436fdd8f6eb" />

**Figure 6: Removing a File**

---

# Task 3: Understanding Users and Permissions

## Objective

Learn how Linux users, ownership, and permissions improve security.

---

# Step 1: Create a New User

Run:

```bash
sudo adduser devopsuser
```

Follow the prompts and create a password.

### Verification

```bash
id devopsuser
```

### Screenshot

**Figure 7: Creating a New User**

---

# Step 2: Create a Test File

Run:

```bash
touch securefile.txt
```

Verify:

```bash
ls -l securefile.txt
```

### Screenshot

<img width="1214" height="740" alt="image" src="https://github.com/user-attachments/assets/0772714c-18e4-4ee2-9464-9805fa9466de" />

**Figure 8: Test File Creation**

---

# Step 3: Modify File Permissions

Run:

```bash
chmod 640 securefile.txt
```

Verify:

```bash
ls -l securefile.txt
```

Expected output:

```text
-rw-r----- 1 user user 0 date securefile.txt
```

### Permission Breakdown

| Value | Meaning |
|---------|-----------|
| 6 | Read + Write |
| 4 | Read Only |
| 0 | No Access |

### Screenshot

<img width="1130" height="126" alt="image" src="https://github.com/user-attachments/assets/ab6af857-4f9f-4011-9fba-2f0f6de68035" />

**Figure 9: File Permission Configuration**

---

# Step 4: Change File Ownership

Run:

```bash
sudo chown devopsuser securefile.txt
```

Verify:

```bash
ls -l securefile.txt
```

Expected output:

```text
-rw-r----- 1 devopsuser user 0 date securefile.txt
```

### Screenshot

<img width="1232" height="298" alt="image" src="https://github.com/user-attachments/assets/6a5df671-02dc-4af1-9a4f-673181cfdc82" />

**Figure 10: File Ownership Verification**

---

# Security Benefits

User and permission management improves security by:

- Restricting unauthorized access
- Protecting sensitive configuration files
- Enforcing least-privilege principles
- Increasing accountability
- Reducing accidental system modifications

In DevOps environments, proper access control protects automation scripts, deployment pipelines, application secrets, and infrastructure resources.

---

# Lab Summary

In this lab, you:

- Compared Linux and Windows for DevOps automation
- Practiced essential Linux command-line operations
- Created and managed Linux users
- Configured file permissions and ownership
- Applied security principles used in real-world DevOps environments

These operating system fundamentals provide the foundation for advanced DevOps practices such as Infrastructure as Code (IaC), Configuration Management, CI/CD pipelines, and cloud automation.

---

# Screenshots Checklist

- [ ] Figure 1: Linux Operating System Verification (`uname -a`)
- [ ] Figure 2: Listing Files and Directories (`ls -l`)
- [ ] Figure 3: Navigating Directories (`cd /var/log`)
- [ ] Figure 4: Creating a Directory (`mkdir devops_project`)
- [ ] Figure 5: Viewing File Contents (`cat config.txt`)
- [ ] Figure 6: Removing a File (`rm config.txt`)
- [ ] Figure 7: Creating a New User (`sudo adduser devopsuser`)
- [ ] Figure 8: Test File Creation (`touch securefile.txt`)
- [ ] Figure 9: File Permission Configuration (`chmod 640 securefile.txt`)
- [ ] Figure 10: File Ownership Verification (`chown devopsuser securefile.txt`)

---

# Author

**Name:** Your Name  
**Course:** DevOps  
**Project:** Critical Thinking Project – Operating System Basics in DevOps Automation and Scaling
