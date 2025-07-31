## 🎯 Challenge 9: Listing and Killing Processes

### 🧠 Objective
Learn how to identify and terminate running processes on your system using commands like `ps`, `grep`, and `kill`.

---

### 🛠️ Steps

#### ✅ Step 1: Start a Background Process
Open a **new terminal** and run a long-duration process:
```bash
sleep 1000
```

<img width="558" height="25" alt="Screenshot 2025-07-31 222240" src="https://github.com/user-attachments/assets/bbde4685-7654-4e53-847a-9311a393de77" />

Leave this terminal open.

---

#### ✅ Step 2: Identify the Process ID (PID)
In the **original terminal**, list all processes and filter for `sleep 1000`:
```bash
ps aux | grep "sleep 1000"
```

<img width="885" height="31" alt="Screenshot 2025-07-31 222202" src="https://github.com/user-attachments/assets/8143a9d3-ddf9-4912-a34d-d0846e146ad7" />

Expected output (example):
```
your_username 1234  0.0  0.0  12340  1000 pts/0  S+  22:30  0:00 sleep 1000
your_username 5678  0.0  0.0  12340  1000 pts/1  S+  22:30  0:00 grep sleep 1000
```

<img width="1236" height="49" alt="Screenshot 2025-07-31 222209" src="https://github.com/user-attachments/assets/6db4a3ff-d7b8-4fa2-8748-0aaeb5584480" />

> 🔍 The **PID** is the number in the **second column** of the line with `sleep 1000` (e.g., `1234`).

---

#### ✅ Step 3: Kill the Process
Use the `kill` command to terminate the process:
```bash
kill 1234
```

<img width="711" height="28" alt="Screenshot 2025-07-31 222215" src="https://github.com/user-attachments/assets/e93dd1c2-0a98-4cbf-a49c-c1c932b35f5f" />

> Replace `1234` with the actual PID you found.

---

#### ✅ Step 4: Verify the Process is Terminated
Run the same `ps aux | grep` command again:
```bash
ps aux | grep "sleep 1000"
```

<img width="1271" height="53" alt="Screenshot 2025-07-31 222221" src="https://github.com/user-attachments/assets/bacd5589-ce84-4222-b075-955ab2228d4d" />

Expected output:
```
your_username 5678  0.0  0.0  12340  1000 pts/1  S+  22:30  0:00 grep sleep 1000
```
> ✅ Only the `grep` line should be shown — the `sleep` process is no longer running.

---

<img width="424" height="44" alt="Screenshot 2025-07-31 222248" src="https://github.com/user-attachments/assets/b9ca3d58-f80f-443e-bdde-fc7806845692" />


### 🛡️ Note:
If the process is **stubborn** and doesn't terminate, use a forceful kill:
```bash
kill -9 [PID]
```
But prefer the normal `kill` for graceful shutdowns.

---


- 🧼 **After Killing (Verification):**
  ```bash
  ps aux | grep "sleep 1000"
  ```

---
