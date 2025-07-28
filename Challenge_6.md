# 🎯 Challenge 6: Viewing File Content

## 🧠 Objective  
Explore different command-line utilities (**cat**, **head**, **tail**) to display the entire content of a file, as well as specific portions (beginning and end).

---

## 🪜 Steps

### ✅ Step 1: Create a Multi-Line Text File

Create a file named `~/learn.txt` with at least 5 distinct lines of text:

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

<img width="1281" height="63" alt="Screenshot 2025-07-28 224027" src="https://github.com/user-attachments/assets/294d254b-e59d-4a91-8c5f-300432d679ae" />


## 🔄 Alternative Method for Challenge 6: Using a Command-Line Text Editor

Instead of using multiple `echo` commands, you can create and edit `~/learn.txt` directly using a **command-line text editor**.

---

### ✅ Using **nano** (Recommended for Beginners)

Open/Create the file with `nano`:

```bash
nano ~/learn.txt
```
<img width="477" height="29" alt="Screenshot 2025-07-28 224007" src="https://github.com/user-attachments/assets/7dd00062-c660-4d1c-af86-cb31828c5868" />


<img width="1841" height="359" alt="Screenshot 2025-07-28 223946" src="https://github.com/user-attachments/assets/f3dc5f68-6420-471d-a6a0-8d44a145fff8" />

Once inside nano:

Type or paste your quotes (at least 5 lines).

Press `Ctrl + O` to save the file.

Press Enter to confirm the filename.

Press `Ctrl + X` to exit nano.

---

### ✅ Step 2: Display Entire File Content

Use cat to display all lines:

```bash
cat ~/learn.txt
```

<img width="1207" height="177" alt="Screenshot 2025-07-28 224143" src="https://github.com/user-attachments/assets/02b3229c-a516-4583-98e5-2da0fe01cd13" />

### ✅ Step 3: Display Only the First 3 Lines

Use head with an option to display the first 3 lines:

```bash
head -n 3 ~/learn.txt
```
<img width="1110" height="86" alt="Screenshot 2025-07-28 224102" src="https://github.com/user-attachments/assets/be1f24e6-469d-4489-a881-eadfdfe92c0d" />

### ✅ Step 4: Display Only the Last 2 Lines

Use tail with an option to display the last 2 lines:

```bash
tail -n 2 ~/learn.txt
```

<img width="1091" height="78" alt="Screenshot 2025-07-28 224110" src="https://github.com/user-attachments/assets/5c569069-6258-4b6c-9119-d734ffbc853d" />
