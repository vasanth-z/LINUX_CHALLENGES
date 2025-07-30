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
ls -l ~ > ~/home_contents.txt
```

### Show the Contents of `home_contents.txt`
Command:

```bash
cat ~/home_contents.txt
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

### 3. Pipe Command Output
Command:

```bash
cat ~/quotes.txt | wc -l
```
Purpose:
Counts the number of lines in quotes.txt using piping.
