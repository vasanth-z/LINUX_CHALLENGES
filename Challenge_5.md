# 🎯 Challenge 5: Executable Permissions for Scripts

## 🧠 Objective  
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

### ✅ Step 2: Attempt to Execute Without Permissions (Expected Failure)

Try to run the script directly:

```bash
~/my_script.sh
Expected behavior: Permission denied (because there’s no execute permission yet).
```

### ✅ Step 3: Execute Using the Interpreter (Works without Execute Bit)

Run the script explicitly with the bash interpreter:

```bash
bash ~/my_script.sh
Expected behavior: It should print the message successfully.
```
Expected behavior: It should print the message successfully.

### ✅ Step 4: Grant Executable Permissions

Add execute permission for the owner:

```bash
chmod u+x ~/my_script.sh
```

### ✅ Step 5: Execute With Permissions (Directly)
Run the script again directly:

```bash
~/my_script.sh
```
Expected behavior: Now it works!
