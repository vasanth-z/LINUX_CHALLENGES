# 🎯 Challenge 14: Gzip Compression and Decompression

**Objective**: Learn how to use the `gzip` command to compress a single file to save disk space and how to decompress it back to its original state. This is a common method for handling large files on Linux systems.

---

## 🧪 Steps

### 1. Create a Large Test File
Create a file named `~/large_file.txt` with 1MB of random alphanumeric characters.

```bash
head -c 1M /dev/urandom | tr -dc A-Za-z0-9 > ~/large_file.txt
```

### 🔍 File Size Before Compression
Check size of the original file:
```bash
ls -l ~/large_file.txt
```

### 2. Compress the File

Use the gzip command to compress the file. This replaces large_file.txt with large_file.txt.gz.

```bash
gzip ~/large_file.txt
```

### 📦 File After Compression
Check the new compressed file:

```bash
ls -l ~/large_file.txt.gz
```

### 3. Decompress the File
Use gunzip to decompress and restore the original file.

```bash
gunzip ~/large_file.txt.gz
```

### 🔁 File After Decompression
Verify the file is restored and the .gz file is gone:

```bash
ls -l ~/large_file.txt
```

