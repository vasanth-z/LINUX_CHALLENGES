# 💻 Challenge 1: Directory Tree Creation & Navigation

## 🎯 Objective  
Learn to create nested directories and navigate through them using:  
- Absolute paths.  
- Relative paths  
- Home directory shortcut (`~`)

---

## 🧱 Steps to Follow

### ✅ Step 1: Create the Directory Structure

Open the terminal and run:

```bash
mkdir -p ~/projects/my_project/src/docs
```
<img width="795" height="108" alt="Screenshot 2025-07-23 213936" src="https://github.com/user-attachments/assets/28183411-f0d3-4532-bc80-cd0f7acb3519" />

### ✅ Step 2: Navigate to docs using an Absolute Path

Replace your_username with your actual Linux username:

```bash
cd /home/your_username/projects/my_project/src/docs
```
<img width="592" height="15" alt="Screenshot 2025-07-23 213953" src="https://github.com/user-attachments/assets/49bd6a6b-74d8-402a-ac55-5bf129c4d51b" />

### ✅ Step 3: Navigate back to my_project using a Relative Path

```bash
cd ../../
```
<img width="713" height="54" alt="Screenshot 2025-07-23 214046" src="https://github.com/user-attachments/assets/c47aa160-6d5c-4362-9e46-15905018510a" />

### ✅ Step 4: Navigate back to your Home Directory using Shortcut

```bash
cd ~
```
<img width="544" height="79" alt="Screenshot 2025-07-23 214053" src="https://github.com/user-attachments/assets/c94e381f-3472-4074-adce-0d5be06c1cfa" />

---

## 📌 Directory Structure Verification

```bash
ls -R ~/projects
```
<img width="646" height="285" alt="Screenshot 2025-07-23 214113" src="https://github.com/user-attachments/assets/aae8d5e7-a7d6-4119-8287-0691e2b1b8f0" />

## 📌 Current Directory After Absolute Path Navigation

```bash
pwd
```
<img width="423" height="72" alt="Screenshot 2025-07-23 221632" src="https://github.com/user-attachments/assets/9c938db2-8fb9-4a64-9b5a-c6830c3c2876" />

Expected Output:

```bash
/home/your_username/projects/my_project/src/docs
```
---

## 📋 Command Summary Table

| Command                                                | Purpose                                                               |
|--------------------------------------------------------|-----------------------------------------------------------------------|
| `mkdir -p ~/projects/my_project/src/docs`              | Creates nested directories recursively                                |
| `cd /home/your_username/projects/my_project/src/docs`  | Navigates to `docs` using absolute path                               |
| `cd ../../`                                            | Moves up two directories to reach `my_project` from `docs`            |
| `cd ~`                                                 | Navigates to the home directory using the tilde `~` shortcut          |
| `ls -R ~/projects`                                     | Lists all files and subdirectories recursively inside `~/projects`    |
| `pwd`                                                  | Prints the current working directory                                  |


