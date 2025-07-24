# 🎯 Challenge 2: File Creation, Copying & Moving

## 🧠 Objective

Practice fundamental file manipulation commands:  
- Creating empty files  
- Copying files to different locations with renaming  
- Moving files within the directory structure  

---

## 🪜 Steps

### ✅ Step 1: Create an Empty File

Navigate to the `~/projects/my_project/src` directory (created in challenge 1) and create an empty file named `main.c`.

```bash
cd ~/projects/my_project/src
touch main.c
```
<img width="656" height="93" alt="Screenshot 2025-07-24 090336" src="https://github.com/user-attachments/assets/94467068-0f67-43d8-84a1-84653cd08855" />
<img width="766" height="77" alt="Screenshot 2025-07-24 090503" src="https://github.com/user-attachments/assets/53ec25b7-727d-4b61-b31b-4e2cb9993cde" />


#### Directory Contents After File Creation (After Step 1):

Show the contents of the src directory to confirm main.c was created.

Command:

```bash
ls -l ~/projects/my_project/src/
```
<img width="970" height="106" alt="Screenshot 2025-07-24 090716" src="https://github.com/user-attachments/assets/dd43858a-e435-49c0-affe-639c44260b4d" />

###  ✅ Step 2: Copy and Rename a File

Copy the main.c file from `~/projects/my_project/src` to `~/projects/my_project/docs.`

```bash
cp ~/projects/my_project/src/main.c ~/projects/my_project/docs/mydocs.c
```
<img width="1386" height="157" alt="Screenshot 2025-07-24 090520" src="https://github.com/user-attachments/assets/50057e29-b909-4fc6-bc91-9e3825f018aa" />
<img width="691" height="74" alt="Screenshot 2025-07-24 090528" src="https://github.com/user-attachments/assets/26b0b0d9-0c5e-4638-a173-db120128ab16" />

#### Directory Contents After Copying (After Step 2):

Show the contents of the docs directory to confirm mydocs.c was copied there.

Show the contents of the src directory again to confirm main.c is still there.

Commands:

```bash
ls -l ~/projects/my_project/docs/
ls -l ~/projects/my_project/src/
```
<img width="909" height="55" alt="Screenshot 2025-07-24 090704" src="https://github.com/user-attachments/assets/02342b4f-3736-41e8-9366-50c74a85b99d" />

###  ✅ Step 3: Move a File (Upwards)

Move the file from `~/projects/my_project/docs` to `~/projects/my_project (one level up from docs)`.

```bash
mv ~/projects/my_project/docs/README.md ~/projects/my_project/
```
<img width="1288" height="111" alt="Screenshot 2025-07-24 090632" src="https://github.com/user-attachments/assets/b6c40afc-cd79-495a-81f2-c38e6b287d77" />


#### Directory Contents After Moving (After Step 3):

Show the contents of the my_project directory to confirm mydocs.c is now there.

Show the contents of the docs directory to confirm mydocs.c is no longer there.

Commands:

```bash
ls -l ~/projects/my_project/
ls -l ~/projects/my_project/docs/
```
<img width="905" height="132" alt="Screenshot 2025-07-24 090723" src="https://github.com/user-attachments/assets/4a8df39c-e48f-4d45-93c5-50757377afcc" />
<img width="751" height="86" alt="Screenshot 2025-07-24 090742" src="https://github.com/user-attachments/assets/89586a26-5c57-46b3-81bf-b64a588b7017" />
---
## 📋 Command Summary Table

| Command                                                                 | Purpose                                                                 |
|-------------------------------------------------------------------------|-------------------------------------------------------------------------|
| `cd ~/projects/my_project/src`                                          | Navigates to the `src` directory inside the project                     |
| `touch main.c`                                                          | Creates an empty file named `main.c`                                    |
| `cp ~/projects/my_project/src/main.c ~/projects/my_project/docs/README.md` | Copies `main.c` to the `docs` directory and renames it to `README.md`   |
| `mv ~/projects/my_project/docs/README.md ~/projects/my_project/`       | Moves `README.md` one level up to the `my_project` directory            |
| `ls -l ~/projects/my_project/src/`                                      | Lists the contents of the `src` directory with details                  |
| `ls -l ~/projects/my_project/docs/`                                     | Lists the contents of the `docs` directory with details                 |
| `ls -l ~/projects/my_project/`                                          | Lists the contents of the `my_project` directory with details           |
---
