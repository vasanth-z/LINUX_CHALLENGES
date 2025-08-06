# 🎯 Challenge 14: Gzip Compression and Decompression

**Objective**: Learn how to use the `gzip` command to compress a single file to save disk space and how to decompress it back to its original state. This is a common method for handling large files on Linux systems.

---

## 🧪 Steps

### 1. Create a Large Test File
Create a file named `~/large_file.txt` with 1MB of random alphanumeric characters.

<img width="739" height="26" alt="Screenshot 2025-08-06 223719" src="https://github.com/user-attachments/assets/5aec1f82-3c7e-4c2e-9b1f-e7fbdc9bc4f9" />

```bash
head -c 1M /dev/urandom | tr -dc A-Za-z0-9 > ~/large_file.txt
```
### 🔍 Explanation:
Part	Meaning
`head -c 1M /dev/urandom` :	This takes the first 1 Megabyte (1M) of random binary data from /dev/urandom — a special file in Linux that produces an endless stream of pseudo-random bytes.

`tr -dc A-Za-z0-9` : 	`tr` is used to translate or delete characters. The `-d` flag means delete all characters except those in the set `A-Za-z0-9`, i.e., only keep uppercase letters, lowercase letters, and numbers.
>	Redirects the final filtered output to a file.
`~/large_file.txt`	This is the destination file in your home directory. It stores the final 1MB of random alphanumeric characters.

<img width="770" height="23" alt="Screenshot 2025-08-06 223726" src="https://github.com/user-attachments/assets/3741de08-0715-46e5-855b-4cd75002c31b" />

<img width="885" height="601" alt="Screenshot 2025-08-06 224203" src="https://github.com/user-attachments/assets/136341d3-795a-43ad-b819-0d2e97da0b81" />


### 🔍 File Size Before Compression
Check size of the original file:
```bash
ls -l ~/large_file.txt
```
<img width="836" height="47" alt="Screenshot 2025-08-06 223735" src="https://github.com/user-attachments/assets/95da5eb5-a91d-4c61-a1c3-63b60523f7c1" />

### 2. Compress the File

Use the gzip command to compress the file. This replaces large_file.txt with large_file.txt.gz.

```bash
gzip ~/large_file.txt
```
<img width="779" height="22" alt="Screenshot 2025-08-06 223742" src="https://github.com/user-attachments/assets/0032a78a-0b2a-4e83-b4a1-c3a119e52fab" />


### 📦 File After Compression
Check the new compressed file:

```bash
ls -l ~/large_file.txt.gz
```

<img width="883" height="51" alt="Screenshot 2025-08-06 223748" src="https://github.com/user-attachments/assets/0903d1ba-f9ee-4d46-a0b8-76f19634034a" />

### 3. Decompress the File
Use gunzip to decompress and restore the original file.

```bash
gunzip ~/large_file.txt.gz
```

<img width="740" height="21" alt="Screenshot 2025-08-06 223758" src="https://github.com/user-attachments/assets/fad38fe4-4f1f-4b02-8249-897803c78993" />

### 🔁 File After Decompression
Verify the file is restored and the .gz file is gone:

```bash
ls -l ~/large_file.txt
```

<img width="858" height="40" alt="Screenshot 2025-08-06 224301" src="https://github.com/user-attachments/assets/ea68e12c-8b44-4214-b5ce-541d920b80ad" />

