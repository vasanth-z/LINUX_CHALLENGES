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
### 2️⃣ Create a Symbolic Link
Create a symbolic link to ~/original.txt named ~/symlink_to_original.txt.
A symlink is a pointer to the original file.

```bash
ln -s ~/original.txt ~/symlink_to_original.txt
```

### 3️⃣ Create a Hard Link
Create a hard link to ~/original.txt named ~/hardlink_to_original.txt.
A hard link is a direct reference to the data on the disk.

```bash
ln ~/original.txt ~/hardlink_to_original.txt
```

### Initial File Status (After Step 3)
Show inode numbers and details.
The inode numbers for the original and hard link should be the same.

```bash
ls -li ~/original.txt ~/symlink_to_original.txt ~/hardlink_to_original.txt
```

---

### 4️⃣ Observe the Effects of Deletion
Delete the original file.

```bash
rm ~/original.txt
```
Symlink: Will be broken (points to a non-existing file).

Hard link: Still works because it references the same data block.

### File Status After Deleting Original (After Step 4)
The symlink will be broken, hard link still valid.

```bash
ls -li ~/symlink_to_original.txt ~/hardlink_to_original.txt
```

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

### Content of Symbolic Link (After Step 5 - Expect Error)
```bash
cat ~/symlink_to_original.txt
```







Ask ChatGPT

