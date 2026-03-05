# Linux Lab - Process Investigation

## Objective

Practice identifying and investigating suspicious processes using basic Linux commands.

---

## Commands Practiced

View running processes:

ps aux

Real-time monitoring:

top

Filter processes:

ps aux | grep <process_name>

View specific process details:

ps -p <PID> -f

Terminate a process:

kill <PID>

Force terminate a process:

kill -9 <PID>

---

## Key Concepts Learned

### Process ID (PID)

Every running process has a unique identifier called a **PID**.

Example:

root  3821  92.5  0.4  miner

Here **3821** is the PID.

---

### Parent Process ID (PPID)

Each process is started by another process called the **parent process**.

Example:

UID   PID   PPID   CMD
root  3821  1100   miner

PPID **1100** is the parent process that launched the miner.

Investigating the parent process can reveal how the suspicious process started.

---

### Process Investigation Steps

Typical investigation workflow:

1. Identify suspicious process using `ps aux`
2. Note the PID
3. Inspect process details using `ps -p <PID> -f`
4. Check parent process (PPID)
5. Terminate malicious process if confirmed

---

## Suspicious Indicators

Examples of suspicious processes:

* Very high CPU usage
* Unknown process names
* Processes running as **root**
* Processes started from unusual directories

---

## Example Scenario

A suspicious process appears:

root 3821 92.5 miner

Possible explanation:
An attacker may run a **cryptocurrency miner** on a compromised machine to use system resources for mining.

---

## What I Learned

* How to list and inspect running processes
* How to identify suspicious processes
* How to trace parent processes
* How to terminate malicious processes

---

## Next Steps

* Investigate network activity of processes
* Learn Linux log analysis
* Practice more SOC-style investigation scenarios
