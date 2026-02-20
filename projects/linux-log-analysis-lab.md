# Linux Log Analysis Lab

## Objective
To understand how to search, filter, and analyze data using Linux commands.

---

## Commands Used
- grep
- find
- wc
- cat
- nano

---

## Tasks Performed

### 1. Created Log File
Created a log file and added multiple entries related to user activity and errors.

Example:
nano log.txt

---

### 2. Searched for Specific Keywords

Used grep to find specific patterns in the log file.

Example:
grep "error" log.txt

---

### 3. Counted Occurrences

Counted how many times a specific keyword appears.

Example:
grep -c "error" log.txt

or using pipe:
grep "error" log.txt | wc -l

---

### 4. Case-Insensitive Search

Searched without case sensitivity.

Example:
grep -i "ERROR" log.txt

---

### 5. File Searching

Used find command to locate files.

Examples:
find ~ -name log.txt
find ~/linux-lab -name "*.txt"

---

### 6. Used Pipes for Filtering

Combined multiple commands using pipes.

Example:
cat log.txt | grep "error"

---

## Mini Lab: Log Analysis

Created a file named system.log and analyzed it.

Tasks:
- Found all error entries
- Counted number of errors
- Identified failed login attempts

Examples:
grep "error" system.log
grep -c "error" system.log
grep "failed" system.log

---

## Challenges Faced
- At first I made a mistake using wc --1 instead of wc -l, but I corrected it and understood the difference.

---

## Learning
- grep is useful for searching inside files
- find helps locate files in the system
- wc -l counts number of lines
- Pipes (|) connect multiple commands together
- Linux can be used to quickly analyze large amounts of data

---

## Conclusion
This lab helped me understand how to extract useful information from logs using Linux commands.
