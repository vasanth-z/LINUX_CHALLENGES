## 🎯 Challenge 7: Searching for Text (grep)

### 🧠 Objective
Learn how to effectively search for specific patterns (text strings) within files using the `grep` command, including:
- Basic matching
- Case-insensitive search
- Inverting the match

---

### 🔧 Steps

### 1. Ensure `learn.txt` is Ready:
Ensure you have the `~/learn.txt` file from **Challenge 6**.

If not, re-create it using `echo` commands or a text editor (`nano` recommended). Make sure it contains at least 5–7 lines, and includes:
- A line with the word **"Linux"**
- Some lines with the word **"the"** or **"The"**

  <img width="1789" height="85" alt="Screenshot 2025-07-29 205225" src="https://github.com/user-attachments/assets/1da03a3d-f2d8-4c53-a4b9-971b278e4528" />

<img width="1208" height="208" alt="Screenshot 2025-07-29 205239" src="https://github.com/user-attachments/assets/645eb02c-b70e-459f-aff7-988e0c9cd8d1" />


### 2. Search for Lines Containing "Linux":

Use grep to find and display all lines in ~/quotes.txt that contain the word "Linux".

Command:

```Bash
grep "linux" ~/learn.txt
```

<img width="1052" height="72" alt="Screenshot 2025-07-29 205256" src="https://github.com/user-attachments/assets/a811f947-6d73-477b-ac08-b54c58b8cfef" />


### 3. Search for Lines Containing "the" (Case-Insensitive):

Use grep with an option to find all lines that contain "the", regardless of whether it's "the", "The", or "THE".

Command:

```
grep -i "LINUX" ~/learn.txt
```

```Bash
grep -i "the" ~/learn.txt
```

<img width="931" height="111" alt="Screenshot 2025-07-29 205401" src="https://github.com/user-attachments/assets/325eb887-2f57-499a-a900-fd945f8568d5" />

<img width="1166" height="78" alt="Screenshot 2025-07-29 205414" src="https://github.com/user-attachments/assets/ab7ffd6f-ecbc-474f-a153-ad410daf4f78" />


### 4. Search for Lines NOT Containing "the word you reject":

Use grep with an option to display all lines that do not contain the word " specific word given". This is called inverting the match.

Example : Here I want to reject the word "linux" and the lines coming with linux. So use this command.

Command:

```Bash
grep -v "linux" ~/learn.txt
```

BEFORE:

<img width="1208" height="208" alt="Screenshot 2025-07-29 205239" src="https://github.com/user-attachments/assets/81d67021-90ac-4119-9fac-997abe0a219d" />

AFTER:

<img width="1376" height="131" alt="Screenshot 2025-07-29 205429" src="https://github.com/user-attachments/assets/1c400ad6-8d46-4c0e-b785-40fe606d3b0f" />

---

## 📄 Summary: Commands and Their Purpose

| Command                          | Purpose                                                                 |
|----------------------------------|-------------------------------------------------------------------------|
| `grep "Linux" ~/learn.txt`     | Searches for lines that contain the exact word "Linux".                |
| `grep -i "the" ~/learn.txt`    | Searches for lines containing "the", case-insensitive (e.g., The, THE).|
| `grep -v "linux" ~/learn.txt`| Displays all lines that do **not** contain the word "linux".        |
