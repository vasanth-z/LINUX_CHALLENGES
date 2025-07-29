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


### 2. Search for Lines Containing "Linux":

Use grep to find and display all lines in ~/quotes.txt that contain the word "Linux".

Command:

```Bash
grep "Linux" ~/learn.txt
```


### 3. Search for Lines Containing "the" (Case-Insensitive):

Use grep with an option to find all lines that contain "the", regardless of whether it's "the", "The", or "THE".

Command:

```Bash
grep -i "the" ~/learn.txt
```

### 4. Search for Lines NOT Containing "the word you need":

Use grep with an option to display all lines that do not contain the word " specific word given". This is called inverting the match.

Command:

```Bash
grep -v "question" ~/learn.txt
```

