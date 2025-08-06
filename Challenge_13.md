# 🎯 Challenge 13: Tar Archiving and Compression

## 🧠 Objective:
Learn to use the `tar` command to bundle multiple files and directories into a single archive, and optionally compress that archive. This is essential for creating backups, sharing large sets of files, and moving data between systems.

## Explanation:
The file extension `.tar.gz` is actually a combination of two different technologies used in a specific sequence.

"tar" Full Form: Tape Archive

Usage: The tar command's original purpose was to create archives for backing up data to magnetic tape. Today, its main usage is to bundle multiple files and directories into a single file. It's an archiver, not a compressor.

Key Function: It gathers a collection of files and directories into a single `.tar` file while preserving their metadata, such as file permissions, ownership, and timestamps. Think of it like putting all your documents into a single box.

"gz" Full Form: GNU Zip

Usage: The gzip command's purpose is to compress a single file to make it smaller. It's a compressor, not an archiver.

Key Function: It uses a compression algorithm to reduce the file size.

The Combined Usage: `.tar.gz`
Since tar only archives and gzip only compresses a single file, they are often used together to achieve both functions at once.

The process is:

Use tar to archive a directory (e.g., my_directory) and all its contents into a single file (e.g., my_directory.tar).

Then, use gzip to compress that single my_directory.tar file, resulting in my_directory.tar.gz.

A verbose list is simply a detailed, item-by-item list of what a command is doing. It provides more information than the minimum required.

The word "verbose" means "using or expressed in more words than are needed." In Linux, a verbose output means the command talks more and tells you everything it's doing.
---

## 🛠️ Steps:

### ✅ Step 1: Create a Test Directory with Files:

Create a directory named `~/archive_test` and add a couple of files.

```bash
mkdir ~/archive_test
echo "This is the first file." > ~/archive_test/file1.txt
echo "This is the second file." > ~/archive_test/file2.txt
```
<img width="608" height="21" alt="Screenshot 2025-08-05 211155" src="https://github.com/user-attachments/assets/9340ee22-22ba-43f1-af36-c4b0523b20f9" />

<img width="714" height="38" alt="Screenshot 2025-08-05 211205" src="https://github.com/user-attachments/assets/96c1de86-0acd-4ea5-8519-e2d0fc83b5c9" />

### 🔍 Original Directory Contents (Before Archive)

```bash
ls -l ~/archive_test/
```

<img width="632" height="73" alt="Screenshot 2025-08-05 211214" src="https://github.com/user-attachments/assets/dc618c7f-13ac-4b8b-b099-529b5cbebb79" />

---

### ✅ Step 2: Create a Compressed Tar Archive

Use `tar` to compress the `archive_test` directory into a `.tar.gz` file.

```bash
tar -czvf ~/my_archive.tar.gz ~/archive_test
```
<img width="651" height="16" alt="Screenshot 2025-08-05 211222" src="https://github.com/user-attachments/assets/98cfa531-cd6e-459a-a06c-522c5c00a548" />

<img width="615" height="87" alt="Screenshot 2025-08-05 211235" src="https://github.com/user-attachments/assets/889d90a8-29a3-4fec-b852-2e7b8c9c6111" />


**Flags Explanation**:
- `-c`: Create a new archive
- `-z`: Compress using gzip
- `-v`: Verbose (shows progress)
- `-f`: Specifies filename of archive

---

### ✅ Step 3: Delete the Original Directory

To verify your archive works as a backup, remove the original folder.

```bash
rm -r ~/archive_test
```
<img width="533" height="21" alt="Screenshot 2025-08-05 211243" src="https://github.com/user-attachments/assets/c26e2335-753d-4408-982f-77a2cf639c6c" />

---

### ✅ Step 4: Extract the Archive

Extract the contents into a new directory named `~/extracted_archive`.

```bash
mkdir ~/extracted_archive
tar -xzvf ~/my_archive.tar.gz -C ~/extracted_archive/
```
<img width="776" height="71" alt="Screenshot 2025-08-05 211328" src="https://github.com/user-attachments/assets/b9ac4359-42af-4ea1-8b08-0ac46032d926" />

**Flags Explanation**:
- `-x`: Extract files
- `-z`: Use gzip
- `-v`: Verbose output
- `-f`: Specifies archive file
- `-C`: Destination directory for extraction

---


### 🔍 Original Directory Contents (Before Archive)

```bash
ls -l ~/archive_test/
```
<img width="677" height="32" alt="Screenshot 2025-08-05 211316" src="https://github.com/user-attachments/assets/4c1912f5-06e3-4dfc-8874-70ea2e2dea19" />


---

### 🗃️ Extracted Directory Contents (After Extraction)

```bash
ls -l ~/extracted_archive/archive_test/
```

**Expected Output**:
```
total 8
-rw-rw-r-- 1 your_username your_username 24 Aug  5 14:30 file1.txt
-rw-rw-r-- 1 your_username your_username 25 Aug  5 14:30 file2.txt
```

<img width="598" height="310" alt="Screenshot 2025-08-05 212518" src="https://github.com/user-attachments/assets/afdb6201-fe6f-41e3-bbeb-40063aa9ee1f" />

---

✅ **Success**: You’ve learned how to create, compress, delete, and extract a `.tar.gz` archive — a crucial Linux admin and DevOps skill!

### Summary table

| Command                                               | Purpose                                                                 |
|--------------------------------------------------------|-------------------------------------------------------------------------|
| `mkdir ~/archive_test`                                | Creates a directory named `archive_test` in the home directory.        |
| `echo "This is the first file." > ~/archive_test/file1.txt` | Creates a file `file1.txt` with sample content.                         |
| `echo "This is the second file." > ~/archive_test/file2.txt`| Creates a file `file2.txt` with sample content.                         |
| `tar -czvf ~/my_archive.tar.gz ~/archive_test`        | Creates a compressed `.tar.gz` archive from the `archive_test` folder. |
| `rm -r ~/archive_test`                                | Deletes the original directory to test archive restore capability.     |
| `mkdir ~/extracted_archive`                           | Creates a directory to extract the archive into.                        |
| `tar -xzvf ~/my_archive.tar.gz -C ~/extracted_archive/` | Extracts the archive contents into `~/extracted_archive`.              |
| `ls -l ~/archive_test/`                               | Lists the contents of the original directory before archiving.         |
| `ls -l ~/my_archive.tar.gz`                           | Verifies the archive file was created.                                 |
| `ls -l ~/extracted_archive/archive_test/`             | Verifies the files were successfully extracted from the archive.       |

