# Linux Permissions and Processes Lab

## Objective
To understand file permissions and process management in Linux.

---

## Permissions

### Commands Used
- chmod
- ls -l

### Tasks Performed
- Created a file (secret.txt)
- Changed file permissions using chmod
- Restricted access to the file
- Restored access permissions
- Made a file executable

### Examples

Removed all permissions:
chmod 000 secret.txt

Gave read permission:
chmod 400 secret.txt

Full access:
chmod 777 secret.txt

Made script executable:
chmod 755 script.sh

---

## Processes

### Commands Used
- ps
- top
- kill

### Tasks Performed
- Started a process using sleep command
- Viewed running processes using ps
- Monitored system using top
- Killed a running process

### Example

Start process:
sleep 1000

View processes:
ps aux

Kill process:
kill <PID>

Force kill:
kill -9 <PID>

---

## Challenges Faced
At first I was confused about chmod numbers, but after practicing I understood how they work.

---

## Learning
- File permissions control access to files
- Numeric values in chmod represent permissions (4 = read, 2 = write, 1 = execute)
- Processes can be monitored and terminated
- Linux gives full control over system behavior
