# Linux Basics - Viewing and Filtering Logs with journalctl

## 📌 Overview

Today I practiced viewing system logs using `journalctl` and filtering them using `grep`. This helps in understanding system activity and identifying important events.

---

## 🧠 What is journalctl?

`journalctl` is used to view logs collected by systemd.
It shows system events such as service activity, user actions, and errors.

---

## ⚙️ Commands Practiced

### View recent logs

sudo journalctl -n 20

* Displays the last 20 log entries
* Useful for checking recent system activity

---

### Monitor logs in real time

sudo journalctl -f

* Shows logs as they are generated
* Useful for live monitoring

---

### Filter logs using grep

sudo journalctl | grep sudo

* Shows logs related to sudo usage

---

### Find failed events

sudo journalctl | grep -i failed

* Displays failed operations such as login failures

---

### Combine recent logs with filtering

sudo journalctl -n 20 | grep sudo

* Shows recent sudo activity only

---

## 🔍 Key Observations

* Logs contain timestamps, services, and messages
* `journalctl` provides centralized system logs
* `grep` helps filter relevant information
* Combining commands improves efficiency

---

## 📸 Example Outputs

### Last 20 Logs

![Last 20 Logs](../images/journalctl-last20.png)

---

### Sudo Activity

![Sudo Logs](../images/journalctl-sudo.png)

---

### Failed Events

![Failed Logs](../images/journalctl-failed.png)

---

## 🧩 What I Learned

* How to view logs using `journalctl`
* How to monitor logs in real time
* How to filter logs using `grep`
* How to identify important events like sudo usage and failures

---

## 🚀 Next Steps

* Practice identifying login activity in logs
* Perform a basic log investigation
* Learn advanced filtering techniques
