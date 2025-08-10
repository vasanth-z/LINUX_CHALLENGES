# 🎯 Challenge 18: Advanced Permissions (Sticky Bit & SUID/SGID)

## Objective  
Understand and apply advanced file permissions that control directory behavior (**sticky bit**) and program execution (**SUID/SGID**). These are critical concepts for securing multi-user systems.

## Key Concepts
The Sticky Bit (t): This permission is used on directories, like /tmp or shared project folders. Its main purpose is to prevent users from deleting files that don't belong to them, even if they have write permissions to the directory. It ensures that only the file's owner (or root) can remove their own files.

Set User ID (SUID) (s): This permission allows an executable file to run with the permissions of its owner. This is essential for programs like passwd, which must be able to modify a sensitive file (/etc/shadow) that only the root user can normally access. SUID lets a regular user run passwd, and the program temporarily assumes root's permissions to perform its task.

Set Group ID (SGID) (s): Similar to SUID, SGID allows a program to run with the permissions of its group owner. For directories, its most common use is to ensure that all new files and subdirectories created within that directory automatically inherit the group ownership of the parent directory. This simplifies file sharing and collaboration within a specific group.

---

## Steps  

### 1️⃣ Create a Shared Directory with a Sticky Bit  
The sticky bit ensures only the file's **owner** can delete it, even in a world-writable directory.

```bash
sudo mkdir /shared_folder
sudo chmod 1777 /shared_folder
sudo chown your_username:your_group /shared_folder
```

- 1 in 1777 → Sticky bit

- 777 → Read, write, execute permissions for all

  ---

### 2️⃣ Simulate Multi-User Behavior
Create a file as your user, then try deleting it as another user.

```bash
touch /shared_folder/my_file.txt
sudo -u nobody rm /shared_folder/my_file.txt
```
Expected:

```bash
rm: cannot remove '/shared_folder/my_file.txt': Operation not permitted
```

----

### 3️⃣ Explore SUID (Set User ID) Bit
SUID lets a program run with the owner’s permissions.

```bash
ls -l /usr/bin/passwd
```
Expected example:

```bash
-rwsr-xr-x 1 root root 54264 May 18 2023 /usr/bin/passwd
(s in the owner's execute position indicates SUID)
```

The `s` you're seeing in a file's permission string is a special permission bit. It's a powerful and important security feature in Linux that changes how a file is executed.

----

### 4️⃣ Explore SGID (Set Group ID) Bit
SGID on a directory makes new files inherit the group of the parent directory.

```bash
mkdir ~/sgid_test
chmod g+s ~/sgid_test
ls -ld ~/sgid_test
```
Expected example:

```arduino
drwxr-sr-x 2 your_username your_group 4096 Aug 10 18:35 /home/your_username/sgid_test
(s in the group execute position indicates SGID)
```

----

### 🧹 Cleanup (Optional)
```bash
sudo rm -r /shared_folder
rm -r ~/sgid_test
```
