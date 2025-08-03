# 🎯 Challenge 5: Executable Permissions for Scripts

## 🧠 Objective :
Understand the concept of **executable permissions**, how to grant them to a script, and the difference between executing a script **directly** versus **passing it to an interpreter**.

---

## 🪜 Steps

### ✅ Step 1: Create a Simple Shell Script

Create a new file named `~/my_script.sh` in your home directory and add a **shebang line** with a simple echo command:

```bash
echo '#!/bin/bash' > ~/my_script.sh
echo 'echo "Hello from my script!"' >> ~/my_script.sh
```
`Note: The >> appends to the file, while > would overwrite it.`

<img width="1054" height="51" alt="Screenshot 2025-07-27 221354" src="https://github.com/user-attachments/assets/283f7332-b040-42aa-974a-d89c9bcee70c" />

### ✅ Step 2: Attempt to Execute Without Permissions (Expected Failure)

Try to run the script directly:

```bash
~/my_script.sh
Expected behavior: Permission denied (because there’s no execute permission yet).
```
<img width="935" height="57" alt="Screenshot 2025-07-27 221402" src="https://github.com/user-attachments/assets/a64e1196-e193-43a3-85ff-2d89a6124915" />

### ✅ Step 3: Execute Using the Interpreter (Works without Execute Bit)

Run the script explicitly with the bash interpreter:

```bash
bash ~/my_script.sh
Expected behavior: It should print the message successfully.
```
<img width="919" height="49" alt="Screenshot 2025-07-27 221409" src="https://github.com/user-attachments/assets/b6e1ff9f-259a-4627-a74d-98b57e4b9904" />

Expected behavior: It should print the message successfully.

### 📌 Initial Script Permissions (Before chmod)
```bash
ls -l ~/my_script.sh
```
Expected Output (Example):
```
-rw-rw-r-- 1 your_username your_username 31 Jul 27 21:30 my_script.sh
```
<img width="959" height="33" alt="Screenshot 2025-07-27 221423" src="https://github.com/user-attachments/assets/e7efbfd1-c5f9-4a13-b67a-859eb1c84771" />

<img width="1051" height="51" alt="Screenshot 2025-07-27 221430" src="https://github.com/user-attachments/assets/2262882d-6b7e-4c3b-a426-8885f3e62ca6" />

### ✅ Step 4: Grant Executable Permissions

Add execute permission for the owner:

```bash
chmod u+x ~/my_script.sh
```
<img width="1043" height="79" alt="Screenshot 2025-07-27 221450" src="https://github.com/user-attachments/assets/afb89248-034c-4b8e-86ce-2a5e14ef0c8b" />

### 📌 Script Permissions After Granting Execute (After Step 4)
```bash
ls -l ~/my_script.sh
```
<img width="1043" height="79" alt="Screenshot 2025-07-27 221450" src="https://github.com/user-attachments/assets/7c09a4b8-bbf5-40bc-b15b-a6ecc7242e2d" />


### ✅ Step 5: Execute With Permissions (Directly)

Run the script again directly:
```bash
~/my_script.sh
```
<img width="886" height="56" alt="Screenshot 2025-07-27 221555" src="https://github.com/user-attachments/assets/cd881097-ac95-4a9e-9399-e5a44aad4ed9" />

Expected behavior: Now it works!

## 📋 Command Summary Table

| Command                                             | Purpose                                                                 |
|-----------------------------------------------------|-------------------------------------------------------------------------|
| `echo '#!/bin/bash' > ~/my_script.sh`              | Creates a new file `my_script.sh` and adds the shebang line            |
| `echo 'echo "Hello from my script!"' >> ~/my_script.sh` | Appends an echo statement to the script                                |
| `~/my_script.sh`                                    | Attempts to execute the script directly (fails without execute bit)    |
| `bash ~/my_script.sh`                               | Executes the script using the `bash` interpreter (works without `x`)   |
| `chmod u+x ~/my_script.sh`                          | Grants execute (`x`) permission to the owner of the script             |
| `ls -l ~/my_script.sh`                              | Lists detailed file permissions and verifies changes                   |

