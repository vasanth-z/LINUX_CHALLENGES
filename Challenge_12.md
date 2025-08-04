## 🎯 Challenge 12: Pinging a Website

**Objective:**  
Learn to use the `ping` command to test network connectivity and measure the round-trip time to a remote host. This is the first and most common tool for troubleshooting basic network issues.

---
### Explanation:

In the command ping -c 4 google.com, the 4 is a number that tells the ping command how many packets to send.

Here's a breakdown:

ping: The main command.

`-c`: This is a command-line option or "flag". It stands for "count".

`4`: This is the value for the `-c` option. It specifies that ping should send exactly 4 ICMP (Internet Control Message Protocol) packets to the destination.

### 🧪 Steps:

#### ✅ Ping a Public Website a Few Times:
Use the `ping` command to send a small packet to `google.com`.

Use the `-c` flag to limit the number of packets sent to a specific number, such as 4. This prevents the command from running indefinitely.

**Command:**
```bash
ping -c 4 google.com
```

<img width="668" height="18" alt="Screenshot 2025-08-04 194818" src="https://github.com/user-attachments/assets/0c24bffd-2ca8-4b4e-9172-d57d7f6d4fb6" />


<img width="885" height="94" alt="Screenshot 2025-08-04 194831" src="https://github.com/user-attachments/assets/06cd09ea-73d2-461b-affa-2b6d6eed9415" />

> **Note:** Without the `-c` flag, `ping` will continue to run until you stop it manually with `Ctrl + C`.

---

### ✅ Proof of Concept (POC):

To demonstrate successful completion of this challenge, provide the output of the `ping` command. A successful output shows that your machine was able to send and receive packets from `google.com`.

**Command:**
```bash
ping -c 4 google.com
```

**Expected Output (Example - actual IP address and timings may vary):**
```bash
PING google.com (142.250.190.46) 56(84) bytes of data.
64 bytes from maa05s04-in-f14.1e100.net (142.250.190.46): icmp_seq=1 ttl=114 time=4.44 ms
64 bytes from maa05s04-in-f14.1e100.net (142.250.190.46): icmp_seq=2 ttl=114 time=5.67 ms
64 bytes from maa05s04-in-f14.1e100.net (142.250.190.46): icmp_seq=3 ttl=114 time=5.21 ms
64 bytes from maa05s04-in-f14.1e100.net (142.250.190.46): icmp_seq=4 ttl=114 time=4.98 ms

--- google.com ping statistics ---
4 packets transmitted, 4 received, 0% packet loss, time 3004ms
rtt min/avg/max/mdev = 4.444/5.075/5.672/0.435 ms
```

---

### 🔍 Explanation:

- The output shows that **4 packets** were sent and **all 4 were received** (0% packet loss), which means your **network connection to google.com is working**.
- The **time values** (e.g., `4.44 ms`) show the **round-trip time** for each packet.
- The final **summary statistics** provide insights like **minimum, average, and maximum response time**.

```bash
ping -c 4 google.com  # Sends 4 ping requests to google.com and displays the response times
```

### Other Examples:

command:

<img width="675" height="19" alt="Screenshot 2025-08-04 194852" src="https://github.com/user-attachments/assets/c2d35542-5ac6-4c93-ae3e-9d4bc32e9fbd" />

Ouptut:

<img width="801" height="271" alt="Screenshot 2025-08-04 194902" src="https://github.com/user-attachments/assets/efcecbe3-d707-4107-87d7-91bcadf89a40" />


#### Summary table
| Command         | Full Form      | Purpose                                                      |
|-----------------|----------------|--------------------------------------------------------------|
| `ping <domain>` | Packet Internet Groper | Sends ICMP Echo Request packets to test network connectivity to a website or host. |

