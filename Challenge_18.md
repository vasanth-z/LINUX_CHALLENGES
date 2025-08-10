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
<img width="657" height="22" alt="Screenshot 2025-08-10 190242" src="https://github.com/user-attachments/assets/0e123c87-2bef-4e20-b2fc-d5214a53838b" />

<img width="710" height="39" alt="Screenshot 2025-08-10 190250" src="https://github.com/user-attachments/assets/f3716005-0191-4e30-af00-4a8fe0188fe7" />

<img width="739" height="32" alt="Screenshot 2025-08-10 190301" src="https://github.com/user-attachments/assets/5a6766cd-27f6-4d24-ab20-ae1d8de6949d" />

#### For creating groups:

<img width="457" height="21" alt="Screenshot 2025-08-10 190326" src="https://github.com/user-attachments/assets/48bc9af9-4404-4565-9b87-f01cd1a95b2c" />

#### To view groups:

<img width="476" height="16" alt="Screenshot 2025-08-10 190331" src="https://github.com/user-attachments/assets/d59b8225-a919-4bd9-b044-6e8db2b9fb3a" />

<img width="685" height="24" alt="Screenshot 2025-08-10 190350" src="https://github.com/user-attachments/assets/1a4daba2-103d-4b17-ad65-5573f20f188f" />


- 1 in 1777 → Sticky bit

- 777 → Read, write, execute permissions for all

  ---

### 2️⃣ Simulate Multi-User Behavior
Create a file as your user, then try deleting it as another user.

```bash
touch /shared_folder/my_file.txt
sudo -u nobody rm /shared_folder/my_file.txt
```
<img width="742" height="17" alt="Screenshot 2025-08-10 190400" src="https://github.com/user-attachments/assets/d1f56eb2-f2ac-450b-980f-a84be6b0c537" />

<img width="774" height="32" alt="Screenshot 2025-08-10 190406" src="https://github.com/user-attachments/assets/b69dea0e-88c3-46e1-8f27-b055dc6285d8" />


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
<img width="724" height="37" alt="Screenshot 2025-08-10 190423" src="https://github.com/user-attachments/assets/16356d23-4f59-4413-84e9-c698fe5bf3a8" />

The `s` you're seeing in a file's permission string is a special permission bit. It's a powerful and important security feature in Linux that changes how a file is executed.

----

### 4️⃣ Explore SGID (Set Group ID) Bit
SGID on a directory makes new files inherit the group of the parent directory.

```bash
mkdir ~/sgid_test
chmod g+s ~/sgid_test
ls -ld ~/sgid_test
```
<img width="693" height="55" alt="Screenshot 2025-08-10 190431" src="https://github.com/user-attachments/assets/5b992e1b-63e0-4157-a02d-5bf709be2c1f" />

<img width="708" height="25" alt="Screenshot 2025-08-10 190442" src="https://github.com/user-attachments/assets/4422f9a2-236d-419c-8653-4105edfb3384" />

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
# 📜 Challenge 18: Advanced Permissions (Sticky Bit & SUID/SGID) — Commands & Purpose

| Command | Purpose |
|---------|---------|
| `sudo mkdir /shared_folder` | Create a new directory `/shared_folder` with root permissions. |
| `sudo chmod 1777 /shared_folder` | Set **sticky bit** (1) and `777` permissions so all users can read, write, and execute, but only owners can delete their files. |
| `sudo chown your_username:your_group /shared_folder` | Change ownership of the directory to your user and group. |
| `touch /shared_folder/my_file.txt` | Create a new file in the shared folder. |
| `sudo -u nobody rm /shared_folder/my_file.txt` | Simulate another user (`nobody`) trying to delete your file (should fail due to sticky bit). |
| `ls -l /usr/bin/passwd` | Check if **SUID bit** is set on `passwd` (look for `s` in owner execute position). |
| `mkdir ~/sgid_test` | Create a new directory named `sgid_test` in your home directory. |
| `chmod g+s ~/sgid_test` | Set the **SGID bit** so new files inherit the directory's group ownership. |
| `ls -ld ~/sgid_test` | Verify SGID permission (look for `s` in group execute position). |
| `ls -ld /shared_folder` | Check sticky bit on `/shared_folder` (look for `t` at the end of permissions). |
| `sudo rm -r /shared_folder` | Remove the shared folder and its contents. |
| `rm -r ~/sgid_test` | Remove the SGID test directory. |
