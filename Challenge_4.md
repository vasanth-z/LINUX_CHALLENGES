# 🎯 Challenge 4: Understanding Basic Permissions (chmod)

## 🧠 Objective  
Learn how to view and modify basic file permissions using **symbolic modes** (`u`, `g`, `o`, `a` with `+`, `-`, `=`) and understand their impact on **read, write, and execute** access for the **owner**, **group**, and **others**.

## 🔐 Understanding Linux File Permissions

In Linux, every file and directory has **permissions** that control who can read, write, or execute it. Permissions are divided into three categories:

| Category  | Symbol | Description                              |
|-----------|--------|------------------------------------------|
| **User**  | `u`    | The **owner** of the file               |
| **Group** | `g`    | Users who belong to the same **group**  |
| **Others**| `o`    | All **other users** on the system       |
| **All**   | `a`    | Refers to **u + g + o**                |

---

### ✅ Permission Types:

| Symbol | Permission | Meaning                                  |
|--------|------------|------------------------------------------|
| `r`    | Read       | Can view file contents or list directory|
| `w`    | Write      | Can modify file or create/delete files  |
| `x`    | Execute    | Can run file (script/program) or access directory |

---

### ✅ Viewing Permissions:

Use `ls -l` to view permissions:

```bash
ls -l file_name
```
### ✅ Changing Permissions with chmod
Symbolic Method:

```bash
chmod u=rw,go= file.txt   # Owner read/write, no access for group/others
chmod a=r,u+w file.txt    # All can read, owner can write
chmod g+x file.sh         # Add execute for group
```
Numeric Method (Octal):

| Number | Permission | 
|--------|------------|
|  7    |    rwx      | 
|  6    |    rw-      | 
|  4    |    r--      |
|  0    |    ---      |

---

## 🪜 Steps

### ✅ Step 1: Create a Test File

Create a simple text file named `~/test_file.txt` in your home directory with some content:

commands:
```bash
echo "Hello Permissions!" > ~/test_file.txt
```
<img width="1233" height="226" alt="Screenshot 2025-07-26 193905" src="https://github.com/user-attachments/assets/c12c34fb-fe7f-48f9-92f4-236595a95ab4" />

<img width="974" height="38" alt="Screenshot 2025-07-26 193917" src="https://github.com/user-attachments/assets/fba0276b-0d98-4236-ae1b-c51a4afe30a3" />

### 📌 Initial File Creation (Before any chmod)
Show initial permissions after creating the file:

commands:
```bash
ls -l ~/test_file.txt
```
<img width="1110" height="56" alt="Screenshot 2025-07-26 193938" src="https://github.com/user-attachments/assets/3669d067-0c4f-4794-8b93-d392f1ef6038" />

### ✅ Step 2: Set Permissions – Owner Read/Write Only

Only the owner can read and write. No one else (group or others) should have access:

```bash
chmod u=rw,go= ~/test_file.txt
```
<img width="979" height="108" alt="Screenshot 2025-07-26 193948" src="https://github.com/user-attachments/assets/701d8bb1-cfae-4995-bc90-9a46911033a0" />

### 📌 Permissions After Step 2 (Owner Read/Write Only)
```bash
ls -l ~/test_file.txt
```

Expected Output:
```
-rw------- 1 your_username your_username 19 Jul 26 19:20 test
```

### ✅ Step 3: Verify Permissions (Owner Read/Write)

Check the detailed permissions:
```bash
ls -l ~/test_file.txt
```
<img width="979" height="108" alt="Screenshot 2025-07-26 193948" src="https://github.com/user-attachments/assets/04ee8df9-83cd-414a-9326-0c6244650382" />

### ✅ Step 4: Set Permissions – Everyone Can Read, Owner Can Write

Everyone can read, and the owner can write:

```bash
chmod a=r,u+w ~/test_file.txt
```
<img width="1056" height="96" alt="Screenshot 2025-07-26 193954" src="https://github.com/user-attachments/assets/f5d057bc-555c-49cf-9a04-199c781f3596" />

Alternative Command:
```
chmod u=rw,go=r ~/test_file.txt
```
(Both achieve the same result.)

### ✅ Step 5: Verify Permissions (Everyone Read, Owner Write)

Check the updated permissions:
```bash
ls -l ~/test_file.txt
```
<img width="1056" height="96" alt="Screenshot 2025-07-26 193954" src="https://github.com/user-attachments/assets/cc630a43-f6f8-4e59-ae34-bcc80e691b3b" />

### NOTE:
To view (OR) print the content saved in the `echo file` :
command:
```bash
cat test.txt
```
<img width="1059" height="66" alt="Screenshot 2025-07-26 194100" src="https://github.com/user-attachments/assets/017b767e-e108-4c02-9e46-ff94b7156870" />


## 📋 Command Summary Table

| Command                                      | Purpose                                                                 |
|---------------------------------------------|-------------------------------------------------------------------------|
| `echo "Hello Permissions!" > ~/test_file.txt` | Creates a file named `test_file.txt` with the text "Hello Permissions!" |
| `chmod u=rw,go= ~/test_file.txt`           | Sets permissions so only the owner can **read and write**; no access for group and others |
| `ls -l ~/test_file.txt`                    | Displays detailed file permissions and attributes                      |
| `chmod a=r,u+w ~/test_file.txt`            | Grants **read access to all** and **write access only to the owner**   |
| `chmod u=rw,go=r ~/test_file.txt`          | Alternative way to give owner read/write and group/others read-only    |
