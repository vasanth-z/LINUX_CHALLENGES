# 🎯 Challenge 3: Deleting Files and Directories Safely

## 🧠 Objective:
Understand the behavior of file and directory deletion commands (`rm` and `rmdir`), specifically the difference between deleting empty and non-empty directories, and how to use recursive deletion.

---

## 🛠️ STEPS:

### 1. Create a Test Directory and File:

Create a new directory and add a file inside it.

command:
```bash
mkdir ~/temp_stuff
touch ~/temp_stuff/junk.txt
```
<img width="1640" height="116" alt="Screenshot 2025-07-25 213143" src="https://github.com/user-attachments/assets/fbdc7c01-1846-4004-b656-c52b483f2df9" />

<img width="433" height="50" alt="Screenshot 2025-07-25 213156" src="https://github.com/user-attachments/assets/90648a7b-9478-4874-a2b1-9b182e860ea0" />
---

<img width="571" height="82" alt="Screenshot 2025-07-25 213203" src="https://github.com/user-attachments/assets/dfc450aa-b5c0-4ddf-ba2e-8a52dcc450fb" />

### Directory Contents After Creation

Show the contents of ~/temp_stuff to confirm junk.txt is inside.

Command:
```Bash
ls -l ~/temp_stuff/
```
<img width="703" height="86" alt="Screenshot 2025-07-25 213212" src="https://github.com/user-attachments/assets/85e20fff-be6c-4671-ba01-7c71e88082cb" />

### Attempt to Delete a Non-Empty Directory (Expected Failure)

Try to delete the directory using rmdir (this will fail because it's not empty).

command:
```bash
rmdir ~/temp_stuff
```
<img width="750" height="60" alt="Screenshot 2025-07-25 213249" src="https://github.com/user-attachments/assets/f6660366-8995-441f-be25-ac744e02ec92" />

### Error Message from Failed rmdir Attempt (After Step 2):

Show the error output you receive when trying to rmdir a non-empty directory.

Command:

```Bash
rmdir ~/temp_stuff
```
Expected Output :
```
rmdir: failed to remove '~/temp_stuff': Directory not empty
```
<img width="750" height="60" alt="Screenshot 2025-07-25 213249" src="https://github.com/user-attachments/assets/f01272ef-9414-4fe5-aefe-ca646f7b80c2" />

### 3. Delete the File Inside the Directory

Remove the file junk.txt from the directory.
```bash
rm rm ~/temp_stuff/junk.txt
```
<img width="565" height="79" alt="Screenshot 2025-07-25 213321" src="https://github.com/user-attachments/assets/6d6f3608-aa57-42ba-be35-4557cd5ae129" />

###📂 Directory Status Before Deletion:
```
ls -l ~/temp_stuff/
```
<img width="566" height="82" alt="Screenshot 2025-07-25 213341" src="https://github.com/user-attachments/assets/a098939b-afd0-47d2-a14b-7b56579bb271" />

 Expected Output:
 ```
total 0
```

### 4. Delete the Now Empty Directory

Now that it's empty, delete the directory.

```bash
rmdir ~/temp_stuff
```
<img width="518" height="55" alt="Screenshot 2025-07-25 213353" src="https://github.com/user-attachments/assets/60f21f2e-4933-4a15-af94-ac65ed3958e5" />

#### ✅ Confirmation of temp_stuff Deletion

```
ls -d ~/temp_stuff/
```

Expected Output:

```
ls: cannot access '/home/your_username/temp_stuff/': No such file or directory
```
<img width="908" height="63" alt="Screenshot 2025-07-25 213359" src="https://github.com/user-attachments/assets/0e9bc24b-ea40-49be-ac2d-ae45f5385f31" />


## 📋 Command Reference Table

| Command                        | Purpose                                                                 |
|-------------------------------|-------------------------------------------------------------------------|
| `mkdir ~/temp_stuff`          | Creates a new directory named `temp_stuff` in the user's home directory |
| `touch ~/temp_stuff/junk.txt` | Creates an empty file named `junk.txt` inside the `temp_stuff` directory |
| `rmdir ~/temp_stuff`          | Attempts to remove the directory (only works if it's empty)             |
| `rm ~/temp_stuff/junk.txt`    | Removes the file `junk.txt` from the directory                          |
| `ls -l ~/temp_stuff/`         | Lists detailed contents of the `temp_stuff` directory                   |
| `ls -d ~/temp_stuff/`         | Lists the directory entry itself (not its contents)                     |

---



