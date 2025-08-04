## 🎯 Challenge 12: Pinging a Website

**Objective:**  
Learn to use the `ping` command to test network connectivity and measure the round-trip time to a remote host. This is the first and most common tool for troubleshooting basic network issues.

---

### 🧪 Steps:

#### ✅ Ping a Public Website a Few Times:
Use the `ping` command to send a small packet to `google.com`.

Use the `-c` flag to limit the number of packets sent to a specific number, such as 4. This prevents the command from running indefinitely.

**Command:**
```bash
ping -c 4 google.com
```

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
