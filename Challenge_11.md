## 🎯 Challenge 11: Disk Usage and Free Space (`du`, `df`)

### 🧠 Objective
Learn how to monitor and understand disk space on your Linux system using:
- `du` to check the size of specific directories.
- `df` to view the available and used space on all mounted filesystems.

---

### 🧪 Steps

#### ✅ Step 1: Check Disk Usage of Your Home Directory

Use the `du` (Disk Usage) command with:
- `-s` → summary (just the total)
- `-h` → human-readable format

```bash
du -sh ~
```

**Expected Output (Example):**
```
4.0G	/home/your_username
```

---

#### ✅ Step 2: Check Free Space on All Filesystems

Use the `df` (Disk Free) command with:
- `-h` → human-readable format

```bash
df -h
```

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

---

### 📄 Summary Table: Commands & Purpose

| Command      | Purpose                                                           |
|--------------|-------------------------------------------------------------------|
| `du -sh ~`   | Displays total disk usage of the home directory in readable units |
| `df -h`      | Shows free and used space on all mounted filesystems              |
