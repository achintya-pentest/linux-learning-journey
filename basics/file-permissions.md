# Linux Basics - File Permissions

## 📌 Overview

Linux file permissions control who can read, write, and execute a file. They are a fundamental part of system security and access control.

---

## 🧠 Permission Categories

Every file in Linux has three types of permissions:

* **User (u)** → Owner of the file
* **Group (g)** → Users in the same group
* **Others (o)** → All other users

---

## 🔑 Permission Types

Each category can have the following permissions:

* **Read (r)** → View file contents
* **Write (w)** → Modify the file
* **Execute (x)** → Run the file as a program

---

## 🔍 Permission Representation

Example:

-rwxr-xr--

Breakdown:

* User → rwx (read, write, execute)
* Group → r-x (read, execute)
* Others → r-- (read only)

---

## 🔢 Numeric Representation

Permissions can be represented using numbers:

* r = 4
* w = 2
* x = 1

Examples:

* 7 → rwx
* 6 → rw-
* 5 → r-x
* 4 → r--

Common combinations:

* **755** → rwxr-xr-x
* **644** → rw-r--r--
* **777** → rwxrwxrwx (not secure)

---

## ⚙️ Changing Permissions

Permissions can be modified using the `chmod` command.

### Numeric Mode

chmod 755 file

### Symbolic Mode

chmod u+x file
chmod g-w file
chmod o+r file

---

## 👤 Ownership

Each file has an owner and a group.

Check ownership:

ls -l

Change owner:

sudo chown user file

Change group:

sudo chgrp group file

---

## 🔥 Special Permissions

### SUID (Set User ID)

* File runs with the permissions of the owner
* Represented as `s`

Example:
-rwsr-xr-x

If execute permission is missing:
-rwSr--r--

---

### SGID (Set Group ID)

* File runs with group privileges
* In directories, new files inherit the group

---

### Sticky Bit

* Only the file owner can delete files
* Mainly used on directories like `/tmp`

Example:
drwxrwxrwt

---

## 🧠 Important Concepts

* `chmod u+x` only affects the owner
* `chmod 777` gives full access to everyone
* `s` appears only when execute permission exists
* `S` appears when execute permission is missing
* Sticky bit is mainly used for directories

---

## 🔐 Security Perspective

* Improper permissions can expose sensitive data
* World-writable files (777) increase risk
* SUID files can lead to privilege escalation
* Sticky bit protects shared directories

---

## 🧩 Summary

Linux file permissions are essential for controlling access to files and maintaining system security. Understanding how permissions work helps in both system administration and cybersecurity.
