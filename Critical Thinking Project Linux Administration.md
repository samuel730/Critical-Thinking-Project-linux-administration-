# Critical Thinking Project: Operating System Basics in DevOps Automation and Scaling

## Introduction

In this project, I explored fundamental operating system concepts that are important in DevOps environments. The objective was to compare Linux and Windows for automation tasks, practice basic Linux command-line operations, and learn how user and permission management contributes to system security.

To complete the practical sections of this project, I used an Ubuntu virtual machine running in a Vagrant environment. Throughout the lab, I executed various Linux commands, created users, modified file permissions, and verified system configurations using terminal commands. These activities helped me gain hands-on experience with operating system management tasks that are commonly performed by DevOps engineers.

---

# Task 1: Evaluating Linux and Windows for DevOps Automation

## Comparison of Linux and Windows

As part of this project, I researched Linux and Windows operating systems to determine which platform is more suitable for DevOps automation. I compared both operating systems based on scripting capabilities, package management, container support, performance, and security.

| Feature            | Linux                                | Windows                    |
| ------------------ | ------------------------------------ | -------------------------- |
| Automation         | Bash and Shell Scripts               | PowerShell                 |
| Package Management | APT, YUM, DNF                        | Winget, Chocolatey         |
| Container Support  | Native Docker and Kubernetes Support | Docker Support Available   |
| Performance        | Lightweight                          | Higher Resource Usage      |
| Cost               | Open Source                          | Licensing Required         |
| Security           | Strong Permission Model              | Strong Enterprise Security |

## Findings

From my research, I found that Linux is the preferred operating system in most DevOps environments. Linux offers powerful automation capabilities through Bash scripting and has excellent support for Docker and Kubernetes, which are commonly used for containerized applications.

Windows provides strong automation through PowerShell and integrates well with Microsoft products. However, Linux is more widely used in cloud computing and microservices deployments because of its flexibility, performance, and extensive open-source ecosystem.

## Recommendation

Based on my findings, I recommend Linux as the most suitable operating system for DevOps automation. Linux provides better support for automation tools, container technologies, and cloud-native applications. It is also cost-effective and requires fewer system resources compared to Windows.

To verify the operating system used during this project, I executed:

```bash
uname -a
```

<img width="1236" height="208" alt="image" src="https://github.com/user-attachments/assets/695ed93d-0a99-43cb-8e02-1b961808efcd" />

The output confirmed that I was working on an Ubuntu Linux system running inside a Vagrant virtual machine.

---

# Task 2: Linux Command-Line Operations

## Listing Files and Directories

I began by exploring the contents of my current working directory using the `ls` command.

```bash
ls -l
```

<img width="1222" height="478" alt="image" src="https://github.com/user-attachments/assets/2e2bb241-b735-42e2-862c-5cef5662f151" />

The command displayed files and directories together with details such as permissions, ownership, and file sizes. This helped me understand how Linux presents file information and how administrators can inspect system contents.

---

## Navigating Directories

To practice directory navigation, I moved into the `/var/log` directory using:

```bash
cd /var/log
```

<img width="646" height="104" alt="image" src="https://github.com/user-attachments/assets/daf88c28-58fe-4f70-8e3e-efdf6db06db3" />

I then verified my current location with:

```bash
pwd
```

<img width="596" height="134" alt="image" src="https://github.com/user-attachments/assets/5e2c1613-aa96-4be6-8698-274ccfac89fa" />

The output confirmed that I had successfully navigated to the `/var/log` directory. This exercise helped me understand how administrators move between directories when managing logs and system files.

---

## Creating a Directory

I created a new directory named `devops_project` using:

```bash
mkdir devops_projects
```

<img width="912" height="120" alt="image" src="https://github.com/user-attachments/assets/a66679ba-064d-4ff1-bbcf-174e2f80833f" />

After creating the directory, I verified its existence by running:

```bash
ls
```

<img width="980" height="176" alt="image" src="https://github.com/user-attachments/assets/77ab510b-267d-4180-b465-ec70d2bc3250" />

The new directory appeared in the output, confirming that it had been created successfully. This demonstrated how directories can be created to organize projects, scripts, and deployment files.

---

## Viewing File Contents

To practice working with files, I created a configuration file and displayed its contents.

```bash
echo "DevOps Configuration File" > config.txt
cat config.txt
```

<img width="1222" height="242" alt="image" src="https://github.com/user-attachments/assets/8807866b-8e2c-4164-9dd0-bec8101d02b8" />

The `cat` command displayed the contents of the file exactly as expected. This showed how Linux users can quickly inspect configuration files and logs from the command line.

---

## Removing a File

After creating and viewing the file, I removed it using:

```bash
rm config.txt
```

<img width="642" height="104" alt="image" src="https://github.com/user-attachments/assets/7bae09d4-bd54-4968-9cdc-f67dd6fd3187" />

I verified the deletion by listing the directory contents again with:

```bash
ls
```

<img width="988" height="202" alt="image" src="https://github.com/user-attachments/assets/22074378-ff57-4d2e-9dd3-5d80c937b7b1" />

The file no longer appeared in the output, confirming that it had been successfully removed. This demonstrated how Linux administrators manage and clean up files from the command line.

---

# Task 3: Understanding OS Users and Permissions

## Creating a New User

To understand Linux user management, I created a new user account named `devopsuser`.

```bash
sudo adduser gituser
```

<img width="1172" height="826" alt="image" src="https://github.com/user-attachments/assets/07accd63-f4ec-4f43-9865-454e04627a2a" />

The system prompted me to create a password and enter user information. After the account was created, I verified it using:

```bash
id gituser
```

<img width="1104" height="170" alt="image" src="https://github.com/user-attachments/assets/fc6b53e1-7d3d-4f77-b2f7-e2dc00599871" />

The output displayed the user and group information, confirming that the account had been successfully created.

---

## Creating a Test File

To demonstrate file ownership and permissions, I created a file named `securefile.txt`.

```bash
touch securefile.txt
```

I then checked its details using:

```bash
ls -l securefile.txt
```

<img width="1234" height="150" alt="image" src="https://github.com/user-attachments/assets/79c20405-9bd9-48ac-9bca-ccbab1e5e47b" />

The output displayed the file ownership and permission settings assigned by default.

---

## Modifying File Permissions

I modified the permissions of the file using:

```bash
sudo chmod 640 securefile.txt
```

To verify the change, I executed:

```bash
ls -l securefile.txt
```

<img width="1240" height="186" alt="image" src="https://github.com/user-attachments/assets/179db808-a2e6-47fa-925b-70f2bfe30a82" />

The output showed that the file permissions had changed to `640`.

These permissions allowed the owner to read and write, allowed group members to read the file, and prevented all other users from accessing it. This exercise demonstrated how Linux permissions can be used to secure sensitive files.

---

## Changing File Ownership

Next, I changed ownership of the file to the newly created user account.

```bash
sudo chown devopsuser securefile.txt
```

I verified the ownership change using:

```bash
ls -l securefile.txt
```

The output confirmed that ownership had been transferred successfully to `devopsuser`.

This exercise demonstrated how administrators can assign files to specific users to maintain accountability and access control.

<img width="1218" height="202" alt="image" src="https://github.com/user-attachments/assets/5926f2d4-abdb-4cac-8728-ce1ba1297066" />

---

# Security Benefits of User and Permission Management

Through this exercise, I learned that Linux security relies heavily on proper user and permission management. By controlling ownership and access rights, administrators can restrict access to sensitive resources and reduce the risk of unauthorized modifications.

The principle of least privilege can be implemented through permission management, ensuring that users only have access to the resources required to perform their responsibilities. This is particularly important in DevOps environments where configuration files, deployment scripts, and application secrets must be protected.

---

# Challenges Encountered

During the project, I encountered a minor issue when I attempted to navigate directories using:

```bash
cd directory_name
```

This resulted in an error because `directory_name` was only a placeholder and not an actual directory. I corrected the mistake by navigating to an existing directory and verifying my location with the `pwd` command.

I also spent time understanding how numeric permission values such as `640` translate into actual access rights. Observing the permission changes with the `ls -l` command helped me understand the Linux permission model more clearly.

These challenges improved my troubleshooting skills and reinforced the importance of verifying command outputs.

---

# Conclusion

This project provided practical experience with operating system concepts that are fundamental to DevOps. Through research and hands-on activities, I compared Linux and Windows operating systems, practiced essential Linux command-line operations, and explored user and permission management.

The project demonstrated why Linux is widely adopted in DevOps environments and helped me develop a better understanding of system administration tasks. By completing these exercises, I gained foundational skills that will support future work in automation, configuration management, cloud computing, and infrastructure management.
