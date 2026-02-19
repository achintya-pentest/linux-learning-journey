# Linux Permissions and Processes Lab

## Objective
To understand how file permissions and processes work in Linux and how to control them.

---

## Permissions

### Commands Used
- chmod
- ls -l

### Tasks Performed
- Created a file (secret.txt)
- Modified file permissions using chmod
- Restricted and restored access
- Made a script executable

### Understanding Permissions

Linux permissions are divided into three groups:
- Owner
- Group
- Others

Each permission has a numeric value:
- 4 = read (r)
- 2 = write (w)
- 1 = execute (x)

Permissions are calculated by adding these values.

Examples:
- 7 = rwx (read, write, execute)
- 6 = rw-
- 5 = r-x
- 4 = r--

### Examples

Remove all permissions:
chmod 000 secret.txt

Give read permission to owner:
chmod 400 secret.txt

Give full access:
chmod 777 secret.txt

Make script executable:
chmod 755 script.sh

---

## Processes

### Commands Used
- ps
- ps aux
- top
- kill

### Tasks Performed
- Started a process using the sleep command
- Viewed running processes
- Monitored system activity
- Terminated a running process

### Examples

Start a process:
sleep 1000

View running processes:
ps aux

Monitor system:
top

Kill a process:
kill <PID>

Force kill:
kill -9 <PID>

---

## Challenges Faced
- Initially I was confused about chmod numbers, but after practicing I understood how they work.

---

## Learning
- File permissions control who can access or modify files
- Numeric values in chmod represent permissions (4 = read, 2 = write, 1 = execute)
- Processes are running programs that can be monitored and controlled
- Linux provides full control over system behavior

---

## Conclusion
This lab helped me understand how to manage file access and control running processes in Linux.

