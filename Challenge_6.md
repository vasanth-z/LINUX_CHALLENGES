# 🎯 Challenge 6: Viewing File Content

## 🧠 Objective  
Explore different command-line utilities (**cat**, **head**, **tail**) to display the entire content of a file, as well as specific portions (beginning and end).

---

## 🪜 Steps

### ✅ Step 1: Create a Multi-Line Text File

Create a file named `~/quotes.txt` with at least 5 distinct lines of text:

```bash
echo "The only way to do great work is to love what you do." > ~/quotes.txt
echo "Linux is not Windows." >> ~/quotes.txt
echo "In the beginning, the Universe was created. This has made a lot of people very angry and been widely regarded as a bad move." >> ~/quotes.txt
echo "The internet is a vast and mysterious place." >> ~/quotes.txt
echo "Knowledge is power, guard it well." >> ~/quotes.txt
echo "To be or not to be, that is the question." >> ~/quotes.txt
echo "Never underestimate the power of a good \`grep\`." >> ~/quotes.txt
```
Note: Using `>` for the first line to create/overwrite and `>>` for lines to append.


## 🔄 Alternative Method for Challenge 6: Using a Command-Line Text Editor

Instead of using multiple `echo` commands, you can create and edit `~/quotes.txt` directly using a **command-line text editor**.

---

### ✅ Using **nano** (Recommended for Beginners)

Open/Create the file with `nano`:

```bash
nano ~/quotes.txt
```
Once inside nano:

Type or paste your quotes (at least 5 lines).

Press `Ctrl + O` to save the file.

Press Enter to confirm the filename.

Press `Ctrl + X` to exit nano.

---

### ✅ Step 2: Display Entire File Content

Use cat to display all lines:

```bash
cat ~/quotes.txt
```

### ✅ Step 3: Display Only the First 3 Lines

Use head with an option to display the first 3 lines:

```bash
head -n 3 ~/quotes.txt
```

### ✅ Step 4: Display Only the Last 2 Lines

Use tail with an option to display the last 2 lines:

```bash
tail -n 2 ~/quotes.txt
```
