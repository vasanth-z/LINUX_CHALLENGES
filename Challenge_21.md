# 🎯 Challenge 21: Analyzing Network Connections
Objective: Learn to use the ss (Socket Statistics) command to list and analyze network connections and open ports on your system. This is a crucial skill for troubleshooting network services, checking for security vulnerabilities, and identifying what's running on your machine.

---

## Steps

### List All Active Connections and Listening Sockets:

The ss command is the modern replacement for netstat. Use the following flags to get a comprehensive view of your network activity:

-a: Show all sockets (both listening and non-listening).

-t: Show TCP sockets.

-u: Show UDP sockets.

-n: Show numeric addresses and port numbers (avoids DNS lookups, making it faster).

-p: Show the process (PID) and program name that owns each socket.

Command:

```Bash
ss -atunp
```
<img width="732" height="227" alt="Screenshot 2025-09-11 175956" src="https://github.com/user-attachments/assets/622a0bc0-9a62-43e1-9077-584f84cc68ac" />


### Filter for a Specific Port:

Use the pipe operator (|) and grep to filter the output of the ss command and find connections or listening services on a specific port. A common port to check is SSH (port 22).

Command:

```Bash

ss -atunp | grep ':22'
```
<img width="725" height="105" alt="Screenshot 2025-09-11 180019" src="https://github.com/user-attachments/assets/328f91e1-52be-464c-8cfa-33e39dad22af" />

Identify a Process by Port:

In the output from the previous step, look at the last column. This will show the program name and PID (Process ID) associated with the socket. This tells you which process is using that specific port.
