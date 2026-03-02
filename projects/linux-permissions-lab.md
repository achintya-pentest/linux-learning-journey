# Linux Lab - File Permissions & Special Permissions

## 📌 Lab Objective

Practice Linux file permissions, ownership, and special permissions (SUID, SGID, Sticky Bit) through hands-on commands. Understand how misconfigured permissions can lead to security risks.

---

## 🛠️ Lab Setup

Create a test file:

```bash
touch file1
ls -l file1
```

---

## 🔍 Step 1: Understanding Default Permissions

Check default permissions:

```bash
ls -l file1
```

Example output:

```
-rw-r--r--
```

### Observation:

* User → read, write
* Group → read
* Others → read

---

## 🔢 Step 2: Changing Permissions (Numeric Mode)

Give full permissions:

```bash
chmod 777 file1
ls -l file1
```

### Observation:

```
-rwxrwxrwx
```

* All users have full access
* This is **not secure**

---

Set restricted permissions:

```bash
chmod 644 file1
ls -l file1
```

### Observation:

```
-rw-r--r--
```

* Only owner can write
* Others can only read

---

## ⚙️ Step 3: Symbolic Mode

Modify specific permissions:

```bash
chmod u+x file1
chmod o-x file1
chmod g+w file1
ls -l file1
```

### Observation:

* `u+x` → adds execute to user
* `o-x` → removes execute from others
* Only targeted permissions are modified

---

## 👤 Step 4: Ownership

Check ownership:

```bash
ls -l file1
```

Change owner:

```bash
sudo chown user file1
```

Change group:

```bash
sudo chgrp group file1
```

---

## 🔥 Step 5: SUID (Set User ID)

Apply SUID:

```bash
chmod u+s file1
ls -l file1
```

### Observation:

```
-rwsr-xr-x
```

* File runs with owner privileges
* Represented by `s`

Remove execute and observe:

```bash
chmod 644 file1
chmod u+s file1
ls -l file1
```

### Observation:

```
-rwSr--r--
```

* Capital `S` means no execute permission

---

## 🔥 Step 6: SGID (Set Group ID)

Apply SGID:

```bash
chmod g+s file1
ls -l file1
```

### Observation:

* File runs with group privileges

---

## 🔥 Step 7: Sticky Bit (Directory)

Create directory:

```bash
mkdir testdir
chmod 777 testdir
ls -ld testdir
```

Apply sticky bit:

```bash
chmod +t testdir
ls -ld testdir
```

### Observation:

```
drwxrwxrwt
```

* Only file owner can delete files

---

## 🔍 Step 8: Finding SUID Files

Search for SUID files in the system:

```bash
find / -perm -4000 2>/dev/null
```

Check permissions:

```bash
ls -l /usr/bin/passwd
```

### Observation:

* SUID allows programs to run with elevated privileges

---

## 🧠 Key Observations

* `chmod u+x` only affects the owner
* `chmod 777` gives full access to everyone
* SUID runs files with owner privileges
* `s` vs `S` depends on execute permission
* Sticky bit is mainly used on directories

---

## 🔐 Security Perspective

* SUID files can be used for privilege escalation
* World-writable files (777) are risky
* Misconfigured permissions can expose sensitive data
* Sticky bit protects shared directories like `/tmp`

---

## ⚠️ Potential Risks

* Writable SUID files can lead to root access
* Improper permissions allow unauthorized modification
* Lack of access control increases attack surface

---

## 🧩 Reflection

This lab helped me understand how Linux permissions control access and how misconfigurations can lead to security vulnerabilities. Understanding these concepts is essential for both SOC analysis and penetration testing.

---

## 🚀 Next Steps

* Practice process management commands
* Analyze system logs
* Perform privilege escalation labs
