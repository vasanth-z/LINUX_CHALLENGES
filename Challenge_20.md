# 🎯 Challenge 20: DNS Resolution & Port Scanning
## Objective:
Learn to use fundamental networking tools (dig, nc) to resolve domain names to IP addresses and to check if specific network ports are open and listening on a remote host.

----

## USAGE:

```dig google.com```:
`dig`: This is a command-line tool for querying DNS (Domain Name System) servers. It's used to look up DNS records and diagnose DNS-related issues. dig is a much more powerful and flexible tool than its older counterpart, nslookup.

`google.com`: This is the domain name you want to look up. dig will query the DNS servers to find the IP address(es) associated with this domain.

**Usage**: This command is used to resolve a human-readable domain name (like a website address) to a machine-readable IP address. It's the first step in troubleshooting connectivity issues to verify that the domain name is correctly mapped to an IP address.

----

`nc -vz google.com 80`
`nc`: Stands for netcat. It's a versatile networking utility often called the "Swiss Army knife" of network tools. It can read from and write to network connections.

`-v`: This flag stands for verbose. It tells nc to provide detailed information about what it's doing, such as the connection attempt and the final result.

`-z`: This flag stands for zero-I/O. It's used for scanning or port checking. It tells nc to attempt a connection but not to send any data. This makes the command very fast and efficient for simply checking if a port is open or closed.

`google.com`: The target host you are trying to connect to.

`80`: The port number on the target host. In this case, port 80 is the standard port for HTTP (Hypertext Transfer Protocol) traffic.

**Usage**: This command is a basic form of port scanning. It's used to test if a specific port on a remote server is open and actively listening for connections. A successful connection attempt confirms that the service (e.g., a web server) is running on that port. If the connection is refused, it tells you the port is closed.

----

## Steps
### 1. Resolve a Domain Name's IP Address (dig):

Use the dig command to query a DNS server and find the IP address(es) associated with a domain name like google.com. dig is a powerful tool for DNS diagnostics.

Command:

```Bash

dig google.com
```
Expected output includes an ANSWER SECTION with the IP address(es) (A records).

<img width="813" height="376" alt="Screenshot 2025-08-15 102030" src="https://github.com/user-attachments/assets/30972eca-2f69-464c-84ed-233a7946ca79" />

----

### 2. Check for an Open Port (nc or telnet):

+ Use the nc (netcat) or telnet command to attempt a connection to a specific port on the target host. Port 80 is for HTTP, and port 443 is for HTTPS. A successful connection indicates the port is open.

 + Use the -vz flags with nc for verbose output and zero-I/O mode, which is good for a simple check..

Command:

```Bash
nc -vz google.com 80
```
If the port is open, you'll see a "succeeded" message.

<img width="758" height="37" alt="Screenshot 2025-08-15 102039" src="https://github.com/user-attachments/assets/9548810a-3f71-4bfb-a27c-fc6738c3539a" />

----

### 3. Check for a Closed Port (Verification):

+ Use the same command to check a port that is unlikely to be open on a public web server, like a high, non-standard port (e.g., 8080).

Command:

```Bash
nc -vz google.com 8080
```
A "Connection refused" or "timed out" message confirms the port is closed..

<img width="883" height="57" alt="Screenshot 2025-08-15 102048" src="https://github.com/user-attachments/assets/fc72cd49-e8f9-48ec-81ea-f6ae321f6119" />


