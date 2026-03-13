# Linux Lab 2 – File Permissions and Ownership

## Objective

The goal of this lab is to understand how Linux controls access to files using **permissions and ownership**.
These mechanisms implement **authorization**, which determines what actions users are allowed to perform.

---

## Tools Used

* Linux Terminal
* Basic Linux Commands

---

## Lab Tasks

---

## Task 1 – Create a Test File

Create a new file.

```bash
touch lab2_file.txt
```

Verify the file exists.

```bash
ls
```

---

## Task 2 – View File Permissions

Check the permissions of the file.

```bash
ls -l lab2_file.txt
```

Example output:

```
-rw-r--r-- 1 user user 0 Mar 13 lab2_file.txt
```

### Permission Breakdown

| Symbol | Meaning |
| ------ | ------- |
| r      | Read    |
| w      | Write   |
| x      | Execute |

Permissions are divided into:

* Owner
* Group
* Others

---

## Task 3 – Modify Permissions

Change the file permissions.

```bash
chmod 600 lab2_file.txt
```

Verify the change.

```bash
ls -l lab2_file.txt
```

Expected result:

```
-rw------- lab2_file.txt
```

Meaning:

* Owner → Read and Write
* Group → No access
* Others → No access

---

## Task 4 – Add Execute Permission

Give execute permission to the file.

```bash
chmod +x lab2_file.txt
```

Check permissions again.

```bash
ls -l lab2_file.txt
```

Example output:

```
-rwx------ lab2_file.txt
```

---

## Task 5 – Check Current User

Identify the current user.

```bash
whoami
```

Example output:

```
user name
```

---

## Task 6 – Change File Ownership

Change the file owner to root.

```bash
sudo chown root lab2_file.txt
```

Verify the change.

```bash
ls -l
```

---

## Task 7 – Create a Private File

Create another file.

```bash
touch private.txt
```

Restrict permissions.

```bash
chmod 700 private.txt
```

Check the permissions.

```bash
ls -l private.txt
```

Example output:

```
-rwx------ private.txt
```

Meaning only the **owner** can access the file.


---

## Key Concepts Learned

* File permissions in Linux
* Ownership control
* Authorization through permissions
* Using `chmod` to modify access
* Using `chown` to change file ownership

---

## Security Insight

Improper permissions can expose sensitive files.

Example of risky permission:

```
-rwxrwxrwx
```

This allows **any user to read, modify, or execute the file**, which can create serious security vulnerabilities.

Understanding file permissions is important for **system security and SOC investigations**.
