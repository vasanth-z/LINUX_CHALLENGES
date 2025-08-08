# 🎯 Challenge 16: Finding Files with Specific Criteria

**Objective:**  
Master the `find` command to locate files based on various attributes like size, modification time, and name. This is a crucial skill for system administration and file management.

---

## ✅ Steps

### 1. Create the Test Environment

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
<img width="764" height="23" alt="Screenshot 2025-08-08 224354" src="https://github.com/user-attachments/assets/69a6a3ee-3156-4d1a-a787-c38942adae8a" />
<img width="785" height="70" alt="Screenshot 2025-08-08 224407" src="https://github.com/user-attachments/assets/930c6344-26ad-4332-8aa6-15126d969b78" />
<img width="680" height="26" alt="Screenshot 2025-08-08 224416" src="https://github.com/user-attachments/assets/08c425d9-1c6e-4757-af97-00b8070351b3" />
<img width="675" height="19" alt="Screenshot 2025-08-08 224423" src="https://github.com/user-attachments/assets/2d78b2cd-05f0-4c2a-83c7-c20df0d25173" />

### 2. Find Files Larger than 1 MB

Search for all files within ~/project_x that are larger than 1 megabyte.

```bash
find ~/project_x -type f -size +1M
```

📌 Note: -type f specifies a regular file, and -size +1M looks for files greater than 1MB.

---

### 3. Find Files Modified in the Last 24 Hours

Find all files in ~/project_x that have been modified within the last day.

```bash
find ~/project_x -type f -mtime -1
```

----

### 4. Find All Empty Files

Find and list all files that have a size of zero bytes.

```bash
find ~/project_x -type f -empty
```

### 5. Find All .txt Files

Find all files ending with the .txt extension.

```bash
find ~/project_x -type f -name "*.txt"
```
