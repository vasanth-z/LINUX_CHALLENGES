## 🎯 Challenge 11: Disk Usage and Free Space (`du`, `df`)

### 🧠 Objective:
Learn how to monitor and understand disk space on your Linux system using:
- `du` to check the size of specific directories.
- `df` to view the available and used space on all mounted filesystems.

---

### 🧪 Steps:

#### ✅ Step 1: Check Disk Usage of Your Home Directory

Use the `du` (Disk Usage) command with:
- `-s` → summary (just the total)
- `-h` → human-readable format

```bash
du -sh ~
```

<img width="434" height="21" alt="Screenshot 2025-08-03 214505" src="https://github.com/user-attachments/assets/b9ebef64-686e-445d-9d54-31fd5c3605dc" />

**Expected Output (Example):**
```
4.0G	/home/your_username
```

<img width="402" height="24" alt="Screenshot 2025-08-03 214516" src="https://github.com/user-attachments/assets/bc7f45b7-4843-4c2e-94de-149163dfbd9d" />

---

#### ✅ Step 2: Check Free Space on All Filesystems

Use the `df` (Disk Free) command with:
- `-h` → human-readable format

```bash
df -h
```

<img width="466" height="21" alt="Screenshot 2025-08-03 214527" src="https://github.com/user-attachments/assets/daa7e723-ae75-4caa-94c4-ce8e42ae1d1a" />

**Expected Output (Example):**
```
Filesystem     Size  Used Avail Use% Mounted on
udev           3.9G     0  3.9G   0% /dev
tmpfs          797M  1.7M  796M   1% /run
/dev/sda1       60G   14G   43G  25% /
tmpfs          3.9G     0  3.9G   0% /dev/shm
tmpfs          5.0M     0  5.0M   0% /run/lock
tmpfs          3.9G     0  3.9G   0% /sys/fs/cgroup
/dev/loop0      64M   64M     0 100% /snap/core20/1974
/dev/loop1     115M  115M     0 100% /snap/discord/141/
```

<img width="724" height="146" alt="Screenshot 2025-08-03 214532" src="https://github.com/user-attachments/assets/a2b86f57-a4d6-4c35-9327-befd2066dd3e" />

---

### 📄 Summary Table: Commands & Purpose

| Command      | Purpose                                                           |
|--------------|-------------------------------------------------------------------|
| `du -sh ~`   | Displays total disk usage of the home directory in readable units |
| `df -h`      | Shows free and used space on all mounted filesystems              |
