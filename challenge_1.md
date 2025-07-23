# 💻 Challenge 1: Directory Tree Creation & Navigation

## 🎯 Objective  
Learn to create nested directories and navigate through them using:  
- Absolute paths  
- Relative paths  
- Home directory shortcut (`~`)

---

## 🧱 Steps to Follow

### ✅ Step 1: Create the Directory Structure

Open the terminal and run:

```bash
mkdir -p ~/projects/my_project/src/docs
```

### ✅ Step 2: Navigate to docs using an Absolute Path

Replace your_username with your actual Linux username:

```bash
cd /home/your_username/projects/my_project/src/docs
```

### ✅ Step 3: Navigate back to my_project using a Relative Path

```bash
cd ../../
```

### ✅ Step 4: Navigate back to your Home Directory using Shortcut

```bash
cd ~
```
---

## 📌 Directory Structure Verification

```bash
ls -R ~/projects
```

## 📌 Current Directory After Absolute Path Navigation

```bash
pwd
```

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


