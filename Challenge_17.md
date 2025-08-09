# 🎯 Challenge 17: Symbolic and Hard Links

## Objective
Understand the fundamental difference between **symbolic links (symlinks)** and **hard links**, including how to create them and how deleting the original file affects each type of link.

---

## Steps

### 1️⃣ Create a Test File
Create a file named `~/original.txt` and add some content to it.

```bash
echo "This is the original file content." > ~/original.txt
```
<img width="831" height="19" alt="Screenshot 2025-08-09 220833" src="https://github.com/user-attachments/assets/be5b3730-7b86-4ff7-9c38-4ddc4e71197c" />

### 2️⃣ Create a Symbolic Link
Create a symbolic link to ~/original.txt named ~/symlink_to_original.txt.
A symlink is a pointer to the original file.

```bash
ln -s ~/original.txt ~/symlink_to_original.txt
```
<img width="808" height="19" alt="Screenshot 2025-08-09 220846" src="https://github.com/user-attachments/assets/d8778594-d9ab-4568-b3d9-b85543a02e2b" />

### 3️⃣ Create a Hard Link
Create a hard link to ~/original.txt named ~/hardlink_to_original.txt.
A hard link is a direct reference to the data on the disk.

```bash
ln ~/original.txt ~/hardlink_to_original.txt
```
<img width="680" height="16" alt="Screenshot 2025-08-09 220853" src="https://github.com/user-attachments/assets/aae8b590-6124-45dc-8053-a5ddf35351c2" />

### Initial File Status (After Step 3)
Show inode numbers and details.
The inode numbers for the original and hard link should be the same.

```bash
ls -li ~/original.txt ~/symlink_to_original.txt ~/hardlink_to_original.txt
```
<img width="884" height="91" alt="Screenshot 2025-08-09 220909" src="https://github.com/user-attachments/assets/149c5d52-5080-46a6-88bd-8c8131b43a05" />

---

### 4️⃣ Observe the Effects of Deletion
Delete the original file.

```bash
rm ~/original.txt
```
<img width="547" height="17" alt="Screenshot 2025-08-09 220915" src="https://github.com/user-attachments/assets/59ec7d47-beb1-4cd2-ac32-d3e1a8d277c1" />

Symlink: Will be broken (points to a non-existing file).

Hard link: Still works because it references the same data block.

### File Status After Deleting Original (After Step 4)
The symlink will be broken, hard link still valid.

```bash
ls -li ~/symlink_to_original.txt ~/hardlink_to_original.txt
```
<img width="890" height="95" alt="Screenshot 2025-08-09 220936" src="https://github.com/user-attachments/assets/8ea1f75c-6421-4785-a884-ccde2c4e0f5c" />

----

### 5️⃣ View File Contents and Status
View Hard Link Content

```bash
cat ~/hardlink_to_original.txt
```

View Symbolic Link Content (Expect Error)

```bash
cat ~/symlink_to_original.txt
```

### Content of Hard Link (After Step 5)
```bash
cat ~/hardlink_to_original.txt
```
<img width="646" height="38" alt="Screenshot 2025-08-09 220941" src="https://github.com/user-attachments/assets/f5e0641f-d97b-4396-a7d2-88b91c0fe668" />

### Content of Symbolic Link (After Step 5 - Expect Error)
```bash
cat ~/symlink_to_original.txt
```
<img width="799" height="30" alt="Screenshot 2025-08-09 220947" src="https://github.com/user-attachments/assets/8c5e7c09-5ea6-40ef-b418-de94b5d6c1fa" />

----

| Command | Purpose |
|---------|---------|
| echo "This is the original file content." > ~/original.txt | Creates a file named `original.txt` in the home directory with sample content. |
| ln -s ~/original.txt ~/symlink_to_original.txt | Creates a symbolic link named `symlink_to_original.txt` pointing to `original.txt`. |
| ln ~/original.txt ~/hardlink_to_original.txt | Creates a hard link named `hardlink_to_original.txt` pointing directly to the data of `original.txt`. |
| rm ~/original.txt | Deletes the original file. |
| ls -li ~/original.txt ~/symlink_to_original.txt ~/hardlink_to_original.txt | Lists files with inode numbers and link counts to observe differences between original, symlink, and hard link. |
| ls -li ~/symlink_to_original.txt ~/hardlink_to_original.txt | Lists the symlink and hard link after original is deleted to see which is still functional. |
| cat ~/hardlink_to_original.txt | Displays the content from the hard link (data still accessible). |
| cat ~/symlink_to_original.txt | Attempts to display content from the symlink (will fail after original file deletion). |


