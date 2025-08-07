# 🎯 Challenge 15: Basic Crontab Entry (Task Scheduling)

## 🧠 Objective:
Learn how to schedule repetitive tasks on a Linux system using `crontab`.

## 📝 Steps:

### 1. Open Your Crontab Editor
Use the `-e` flag to edit your user’s crontab file:
```bash
crontab -e
```
### 2. Add the Cron Job

Add the following line to the bottom of the file:

```
* * * * * echo "Hello from cron at $(date)" >> ~/cron_output.log
```
Note: Between every `*` space must be given

🔍 Explanation:

| Field        | Value | Meaning                      |
|--------------|-------|------------------------------|
| Minute       | *     | Every minute                 |
| Hour         | *     | Every hour                   |
| Day          | *     | Every day of the month       |
| Month        | *     | Every month                  |
| Weekday      | *     | Every day of the week        |
| Command      | echo "Hello from cron at $(date)" >> ~/cron_output.log | Appends timestamped message to a log file |

### 3. Save and Exit the Editor

For nano: Press Ctrl + O, then Enter to save, then Ctrl + X to exit.

Terminal will confirm: crontab: installing new crontab

### 4. Wait and Verify:

Wait 2-3 minutes and then check the log file.
Check crontab entry:

```bash
crontab -l
```

#### check the Log file content:
```
cat ~/cron_output.log
```

Expected Output Example:
```bash
Hello from cron at Thu Aug  7 22:01:01 IST 2025
Hello from cron at Thu Aug  7 22:02:01 IST 2025
Hello from cron at Thu Aug  7 22:03:01 IST 2025
```

### ⚠️ CRITICAL: Clean Up! ⚠️
To stop the cron job:

Open crontab again:

```bash
crontab -e
```

Delete the line:

```c
* * * * * echo "Hello from cron at $(date)" >> ~/cron_output.log
```
Save and exit the editor.

----

| Command                                         | Purpose                                                                 |
|-------------------------------------------------|-------------------------------------------------------------------------|
| `crontab -e`                                    | Opens the crontab file for the current user to edit scheduled tasks.   |
| `* * * * * echo "Hello from cron at $(date)" >> ~/cron_output.log` | Cron job that appends current timestamp to a log file every minute.    |
| `crontab -l`                                    | Lists all scheduled cron jobs for the current user.                    |
| `cat ~/cron_output.log`                         | Displays the contents of the log file to verify the cron job ran.      |
