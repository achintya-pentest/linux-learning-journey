# Linux Log Analysis - Notes

## 🧠 Overview

Today I learned the basics of analyzing log files in a Linux environment using command-line tools.

---

## 📂 Log Files

Log files store system and application activity. They are useful for monitoring, troubleshooting, and detecting suspicious behavior.

---

## 🔧 Commands Learned

### 1. Viewing Log Files

```bash
cat access1.log
```

Displays the content of a log file.

---

### 2. Combining Log Files

```bash
cat access1.log access2.log > combined_access.log
```

Combines multiple log files into one file.

**Note:**

* `>` overwrites the file if it already exists
* `>>` can be used to append instead of overwriting

---

### 3. Searching Logs

```bash
grep "192.168.1.10" combined_access.log
```

Searches for a specific pattern (e.g., IP address) inside a log file.

**Use Cases:**

* Finding activity from a specific IP
* Identifying suspicious behavior

---

### 4. Reading Large Logs

```bash
less combined_access.log
```

Allows efficient navigation of large log files.

**Features:**

* Scroll up/down
* Search using `/keyword`

---

## 🧠 Key Concepts

### Event IDs

Event IDs help identify specific types of events in logs (e.g., login success, login failure).

---

### Web Server Logs

Contain information such as:

* IP address
* Request type (GET/POST)
* Status codes (200, 404, etc.)

---

## 🔍 Log Analysis Use Cases

* Detect failed login attempts
* Identify suspicious IP activity
* Analyze web traffic patterns

---

## 🧠 Key Learnings

* Logs contain important system and network activity
* Linux commands can be used to analyze logs
* Searching and filtering logs is important for investigation

---
