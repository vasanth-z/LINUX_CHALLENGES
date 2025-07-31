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
Leave this terminal open.

---

#### ✅ Step 2: Identify the Process ID (PID)
In the **original terminal**, list all processes and filter for `sleep 1000`:
```bash
ps aux | grep "sleep 1000"
```

Expected output (example):
```
your_username 1234  0.0  0.0  12340  1000 pts/0  S+  22:30  0:00 sleep 1000
your_username 5678  0.0  0.0  12340  1000 pts/1  S+  22:30  0:00 grep sleep 1000
```
> 🔍 The **PID** is the number in the **second column** of the line with `sleep 1000` (e.g., `1234`).

---

#### ✅ Step 3: Kill the Process
Use the `kill` command to terminate the process:
```bash
kill 1234
```
> Replace `1234` with the actual PID you found.

---

#### ✅ Step 4: Verify the Process is Terminated
Run the same `ps aux | grep` command again:
```bash
ps aux | grep "sleep 1000"
```

Expected output:
```
your_username 5678  0.0  0.0  12340  1000 pts/1  S+  22:30  0:00 grep sleep 1000
```
> ✅ Only the `grep` line should be shown — the `sleep` process is no longer running.

---

### 🛡️ Note:
If the process is **stubborn** and doesn't terminate, use a forceful kill:
```bash
kill -9 [PID]
```
But prefer the normal `kill` for graceful shutdowns.

---

### ✅ Proof of Concept

- 📌 **Before Killing:**
  ```bash
  ps aux | grep "sleep 1000"
  ```

- 🔪 **Kill Command:**
  ```bash
  kill 1234
  ```

- 🧼 **After Killing (Verification):**
  ```bash
  ps aux | grep "sleep 1000"
  ```

---
