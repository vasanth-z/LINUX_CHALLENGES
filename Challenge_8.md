# 🎯 Challenge 8: Redirection and Piping

## 🧠 Objective
Understand how to:
- Redirect command output to files using `>` and `>>`
- Pipe the output of one command as input to another using `|`

These are essential for automation and data processing in Linux.

---

## ✅ Steps

### 1. Redirect Output to a New File

**Command:**
```bash
ls -l ~ > ~/sample.txt
```

<img width="1141" height="445" alt="Screenshot 2025-07-30 085651" src="https://github.com/user-attachments/assets/234a2d19-209a-4198-bd11-ce38dd2cc725" />

<img width="1011" height="40" alt="Screenshot 2025-07-30 085722" src="https://github.com/user-attachments/assets/7a2325dc-0898-4418-93c8-2b1e17d3f538" />


### Show the Contents of `sample.txt`
Command:

```bash
cat ~/sample.txt
```
Purpose:
Saves the detailed listing of your home directory to sample.txt.
If the file exists, it will be overwritten.

### 2. Append Output to an Existing File
Command:

```bash
df -h >> ~/home_contents.txt
```
Purpose:
Appends the disk usage information to home_contents.txt.
Existing content remains intact.

<img width="856" height="66" alt="Screenshot 2025-07-30 085745" src="https://github.com/user-attachments/assets/d9053a7e-4694-4b4d-bb0d-6821bb4c6d13" />

<img width="725" height="658" alt="Screenshot 2025-07-30 085800" src="https://github.com/user-attachments/assets/76b56797-da8f-41d2-85c5-d359880b4b42" />

### 3. Pipe Command Output
Command:

```bash
cat ~/quotes.txt | wc -l
```
Purpose:
Counts the number of lines in quotes.txt using piping.

<img width="850" height="39" alt="Screenshot 2025-07-30 085821" src="https://github.com/user-attachments/assets/d8c476e9-3b69-4b99-95f1-c96034a51338" />


### 🔄 Challenge 8: Redirection and Piping – Summary

| Command                               | Purpose                                                                 |
|---------------------------------------|-------------------------------------------------------------------------|
| `ls -l ~ > ~/home_contents.txt`       | Redirects the output of `ls -l ~` to a new file, overwriting if it exists |
| `df -h >> ~/home_contents.txt`        | Appends the disk usage info to the existing file without overwriting     |
| `cat ~/quotes.txt | wc -l`            | Pipes the content of `quotes.txt` to `wc -l` to count the number of lines |
| `cat ~/home_contents.txt`             | Displays the full content of `home_contents.txt`                         |

