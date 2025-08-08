# 🎯 Challenge 16: Finding Files with Specific Criteria

**Objective:**  
Master the `find` command to locate files based on various attributes like size, modification time, and name. This is a crucial skill for system administration and file management.

---

## ✅ Steps:

### 1. Create the Test Environment:

Create a sample directory structure with files of different sizes and ages.

```bash
mkdir -p ~/project_x/data ~/project_x/config ~/project_x/logs
touch -t 202401151000 ~/project_x/data/old_data.log
dd if=/dev/zero of=~/project_x/data/large_file.bin bs=1M count=2
touch ~/project_x/config/config.txt
touch ~/project_x/config/empty.conf
echo "Example log entry" > ~/project_x/logs/service.log
```
<img width="811" height="22" alt="Screenshot 2025-08-08 224337" src="https://github.com/user-attachments/assets/895087bd-78dd-4e46-a507-116bee16f379" />

<img width="681" height="17" alt="Screenshot 2025-08-08 224345" src="https://github.com/user-attachments/assets/9d6f588b-7e09-4d79-99cd-a6187f19ae80" />

<img width="785" height="70" alt="Screenshot 2025-08-08 224407" src="https://github.com/user-attachments/assets/930c6344-26ad-4332-8aa6-15126d969b78" />

<img width="680" height="26" alt="Screenshot 2025-08-08 224416" src="https://github.com/user-attachments/assets/08c425d9-1c6e-4757-af97-00b8070351b3" />

<img width="675" height="19" alt="Screenshot 2025-08-08 224423" src="https://github.com/user-attachments/assets/2d78b2cd-05f0-4c2a-83c7-c20df0d25173" />

<img width="759" height="15" alt="Screenshot 2025-08-08 224430" src="https://github.com/user-attachments/assets/3da84666-ca04-479b-840f-4d50a1e4a1dc" />

### 2. Find Files Larger than 1 MB

Search for all files within ~/project_x that are larger than 1 megabyte.

```bash
find ~/project_x -type f -size +1M
```

<img width="720" height="37" alt="Screenshot 2025-08-08 224437" src="https://github.com/user-attachments/assets/f00344a7-90c1-4c0d-980e-e93ce849c452" />

📌 Note: -type f specifies a regular file, and -size +1M looks for files greater than 1MB.

---

### 3. Find Files Modified in the Last 24 Hours:

Find all files in ~/project_x that have been modified within the last day.

```bash
find ~/project_x -type f -mtime -1
```

<img width="763" height="89" alt="Screenshot 2025-08-08 224449" src="https://github.com/user-attachments/assets/67363bc4-d40f-4b2c-a0d4-c3e64cc167d9" />


----

### 4. Find All Empty Files:

Find and list all files that have a size of zero bytes.

```bash
find ~/project_x -type f -empty
```

<img width="853" height="72" alt="Screenshot 2025-08-08 224457" src="https://github.com/user-attachments/assets/0490a726-ffca-484b-9472-753a3e78f71d" />

### 5. Find All `.txt` Files:

Find all files ending with the .txt extension.

```bash
find ~/project_x -type f -name "*.txt"
```

<img width="770" height="38" alt="Screenshot 2025-08-08 224505" src="https://github.com/user-attachments/assets/ae74aa43-7783-49f4-a8b4-96fa25da99cf" />

---

### 📄 Challenge 16: Finding Files with Specific Criteria - Command Summary

| Command | Purpose |
|--------|---------|
| `mkdir -p ~/project_x/data ~/project_x/config ~/project_x/logs` | Creates a nested directory structure for testing. |
| `touch -t 202401151000 ~/project_x/data/old_data.log` | Creates a file with a manually set old timestamp. |
| `dd if=/dev/zero of=~/project_x/data/large_file.bin bs=1M count=2` | Creates a 2MB file filled with zero bytes. |
| `touch ~/project_x/config/config.txt` | Creates a text file in the config directory. |
| `touch ~/project_x/config/empty.conf` | Creates an empty file (0 bytes) in the config directory. |
| `echo "Example log entry" > ~/project_x/logs/service.log` | Adds a line of text to a log file. |
| `find ~/project_x -type f -size +1M` | Finds files larger than 1MB. |
| `find ~/project_x -type f -mtime -1` | Finds files modified within the last 24 hours. |
| `find ~/project_x -type f -empty` | Finds files that are empty (0 bytes). |
| `find ~/project_x -type f -name "*.txt"` | Finds files with a `.txt` extension. |
