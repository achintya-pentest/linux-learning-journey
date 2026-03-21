# Linux Basics - Log Navigation and Filtering

## 📌 Overview

Today I practiced basic Linux commands used to view and search log files. Logs contain system activity and are useful for understanding what is happening on a machine.

---

## 🧠 Commands Practiced

### View logs using less

less /var/log/boot.log

* Used to open and navigate large log files
* Allows scrolling and searching inside the file

---

### Useful keys in less

space → move forward
b → move backward
/keyword → search inside the file
n → next match
q → quit

---

### Search logs using grep

grep service /var/log/boot.log

* Filters lines containing a specific word
* Helps find relevant information quickly

Case-insensitive search:

grep -i error /var/log/boot.log

---

### View recent logs using tail

tail /var/log/boot.log

* Shows the last lines of a log file
* Useful for checking recent events

---

### Combine commands

tail /var/log/boot.log | grep service

* Shows recent log entries filtered by keyword

---

## 🔍 Key Observations

* Log files can be very large, so tools like `less` are important
* `grep` helps filter useful information from logs
* `tail` is useful for viewing recent activity
* Combining commands makes analysis more efficient

---

## 📸 Example Outputs

### Viewing logs with less

![Less Command](../images/less-bootlog.png)

---

### Searching logs using grep

![Grep Command](../images/grep-service.png)

---

### Viewing recent logs using tail

![Tail Command](../images/tail-bootlog.png)

---

## 🧩 What I Learned

* How to navigate large log files
* How to search logs for specific keywords
* How to view recent system events
* How to combine commands for better results

---

## 🚀 Next Steps

* Practice log analysis using journalctl
* Identify login activity and failed attempts
* Apply log filtering in investigation scenarios
