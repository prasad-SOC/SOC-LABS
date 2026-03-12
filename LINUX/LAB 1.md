# Linux Lab 1 – File System Navigation and File Management

## Objective

Learn how to navigate the Linux file system and perform basic file and directory management operations using command-line tools.

## Environment

Recommended environment: Kali Linux or Ubuntu running in a virtual machine.

---

## Commands Covered

| Command | Purpose                           |
| ------- | --------------------------------- |
| pwd     | Display current working directory |
| ls      | List directory contents           |
| cd      | Change directory                  |
| mkdir   | Create directories                |
| touch   | Create files                      |
| cp      | Copy files                        |
| mv      | Move or rename files              |
| rm      | Remove files or directories       |

---

## Lab Setup

Open a terminal and create a working directory for the lab.

```
mkdir soc_linux_lab
cd soc_linux_lab
```

Verify your location.

```
pwd
```

Expected result: The terminal should display the full path of your current directory.

---

## Task 1 – Explore the Directory

List the contents of the current directory.

```
ls
```

Since the directory was just created, it should initially be empty.

---

## Task 2 – Create Directories

Create three directories that simulate folders often used in system environments.

```
mkdir logs scripts data
```

Verify creation:

```
ls
```

Expected output should show:

logs
scripts
data

---

## Task 3 – Create Files

Create example files inside the lab directory.

```
touch system.log access.log script.sh
```

Verify:

```
ls
```

---

## Task 4 – Copy Files

Create a backup copy of a log file.

```
cp system.log system_backup.log
```

Verify:

```
ls
```

---

## Task 5 – Rename a File

Rename a file using the move command.

```
mv access.log network_access.log
```

Verify the change:

```
ls
```

---

## Task 6 – Move Files to a Directory

Move the script file into the scripts directory.

```
mv script.sh scripts/
```

Verify:

```
ls scripts
```

---

## Task 7 – Delete a File

Remove the backup log file.

```
rm system_backup.log
```

Verify removal:

```
ls
```

---

## Task 8 – Remove a Directory

Remove the data directory.

```
rmdir data
```

Verify:

```
ls
```

---

## Expected Skills After Completing the Lab

After completing this lab you should be able to:

• Navigate directories in Linux

• Create and organize files and folders

• Copy, move, rename, and delete files

• Understand the basic Linux file system workflow

---

## SOC Relevance

Security analysts frequently use Linux systems to:

• Navigate server directories

• Locate suspicious files

• Organize investigation artifacts

• Manage log files during incident analysis

These foundational commands support later tasks such as log investigation and malware file analysis.

---

## Conclusion

This lab introduced basic Linux file system operations. Mastering these commands is essential before performing more advanced tasks such as log analysis, system investigation, and security monitoring.
