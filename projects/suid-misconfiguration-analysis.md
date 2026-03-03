# Linux Lab - SUID Misconfiguration Analysis

## 📌 Objective

Understand how SUID works and analyze when it becomes a security risk.

---

## 🧠 Concept Recap

SUID (Set User ID) allows a program to run with the privileges of its owner instead of the user executing it.

If a file is owned by root and has SUID enabled, it runs with root privileges.

Example:

-rwsr-xr-x 1 root root program

---

## 🔎 Scenario 1: Normal SUID Binary

-rwsr-xr-x 1 root root program

Observations:

* Owned by root
* SUID enabled
* Not writable by group or others

Conclusion:
SUID alone is not automatically exploitable. Many legitimate system programs (like passwd) use SUID safely.

---

## 🔎 Scenario 2: Dangerous Combination

-rwsrwxr-x 1 root root program

Observations:

* SUID enabled
* Group has write permission

Why this is dangerous:
If a user in the group can modify this file, they can inject malicious code.
When executed, the program runs as root, leading to privilege escalation.

---

## ⚠️ Key Security Insight

SUID alone → Normal behavior
Writable file alone → Risky
SUID + Writable → Critical vulnerability

This combination can allow attackers to gain elevated privileges.

---

## 🧩 What I Learned

* SUID makes programs run with owner privileges.
* Not all SUID binaries are vulnerable.
* Dangerous permissions usually involve combinations.
* Privilege escalation often depends on misconfiguration, not just one setting.

---

## 🔐 Security Perspective

As a defender (SOC mindset), suspicious changes like:

chmod 777 file
chmod u+s file

could indicate malicious intent or backdoor creation.

Monitoring permission changes is important in detecting privilege escalation attempts.

---

## 🚀 Next Steps

* Practice enumerating SUID files
* Study common privilege escalation patterns
* Learn safe permission configurations
