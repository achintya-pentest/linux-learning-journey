# Linux Basics - Navigating and Searching Logs

## Overview

Today I practiced basic commands used to view and search log files in Linux. Logs contain records of system events and are useful for troubleshooting and security investigations.

---

## Viewing Logs

Log files can be opened using:

less /var/log/boot.log

The `less` command allows viewing large files page by page.

Useful keys inside `less`:

space → move forward one page
b → move backward one page
/keyword → search inside the file
q → quit

---

## Searching Logs

The `grep` command is used to search for specific words or patterns in log files.

Example:

grep service /var/log/boot.log

This displays only lines containing the word **service**.

Case-insensitive search:

grep -i error /var/log/boot.log

---

## Viewing the Latest Log Entries

The `tail` command shows the last lines of a file.

Example:

tail /var/log/boot.log

This is useful when checking the most recent system events.

---

## Combining Commands

Commands can be combined using pipes.

Example:

tail /var/log/boot.log | grep service

This shows the last log entries that contain the word **service
