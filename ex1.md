
# EXPERIMENT 1 – JOB SCHEDULING AND AUTOMATION IN LINUX

**Subject:** Open Source Systems, Agile Tools and Prompt Engineering  
**Name:** Sharon Christy R  
**Register Number:** 26120159

---

## AIM

To automate the execution of shell scripts in Linux using Cron and systemd timers.

## SOFTWARE REQUIREMENTS

1. Ubuntu Linux
2. Bash Shell
3. Cron
4. systemd
5. Text Editor (Nano)

## EXPERIMENT OVERVIEW

In this experiment, a shell script is created to generate a daily project report.

The script is scheduled to execute automatically using:
1. Cron
2. systemd timer

The generated output is stored in a log file and verified.

---

# PART 1 – CREATE A NEW PROJECT DIRECTORY

## STEP 1: OPEN UBUNTU TERMINAL

Open Ubuntu terminal.

Move to the home directory:

```bash
cd ~
```

Create a new project directory:

```bash
mkdir linux-automation-lab
```

Enter the directory:

```bash
cd linux-automation-lab
```

Verify the current location:

```bash
pwd
```

---

# PART 2 – CREATE A SHELL SCRIPT

## STEP 2: CREATE THE DAILY REPORT SCRIPT

Create a new file:

```bash
nano daily_report.sh
```

Enter the following code:

```bash
#!/bin/bash

echo "DAILY AUTOMATION REPORT"
echo "-----------------------"
echo "Project: Software Development"
echo "Status: Successful"
echo "Execution Date: $(date)"
```

Save the file:

1. Press Ctrl + O.
2. Press Enter.
3. Press Ctrl + X.

## STEP 3: GIVE EXECUTION PERMISSION

Run:

```bash
chmod +x daily_report.sh
```

This gives permission to execute the shell script.

## STEP 4: EXECUTE THE SCRIPT

Run:

```bash
./daily_report.sh
```

EXPECTED OUTPUT:

```text
DAILY AUTOMATION REPORT
-----------------------
Project: Software Development
Status: Successful
Execution Date: [current date and time]
```

---

# PART 3 – AUTOMATE USING CRON

## STEP 5: OPEN CRON EDITOR

Run:

```bash
crontab -e
```

If asked to select an editor, choose Nano.

Add the following line at the bottom:

```cron
* * * * * /bin/bash /home/sharon_christy_r/linux-automation-lab/daily_report.sh >> /home/sharon_christy_r/linux-automation-lab/report.log 2>&1
```

This schedules the script to execute every minute and stores the output in report.log.

Save and exit Nano.

NOTE:
If your Ubuntu username is different, replace `sharon_christy_r` with your actual username.

## STEP 6: VERIFY CRON JOB

Run:

```bash
crontab -l
```

This displays the scheduled Cron jobs.

## STEP 7: CHECK GENERATED LOG FILE

Wait approximately one minute.

Run:

```bash
cat report.log
```

EXPECTED OUTPUT:

The log file displays the daily automation report with execution date and time.

Multiple entries may appear because the Cron job executes every minute.

## STEP 8: CHECK CRON SERVICE

Run:

```bash
sudo systemctl status cron
```

If Cron is not running, start it:

```bash
sudo systemctl start cron
```

---

# PART 4 – AUTOMATE USING SYSTEMD TIMER

## STEP 9: CREATE SYSTEMD SERVICE FILE

Create a service file:

```bash
sudo nano /etc/systemd/system/daily-report.service
```

Enter:

```ini
[Unit]
Description=Daily Automation Report

[Service]
Type=oneshot
ExecStart=/bin/bash /home/sharon_christy_r/linux-automation-lab/daily_report.sh
```

Save and exit.

NOTE:
Replace the username in the path if necessary.

## STEP 10: CREATE SYSTEMD TIMER FILE

Create:

```bash
sudo nano /etc/systemd/system/daily-report.timer
```

Enter:

```ini
[Unit]
Description=Run Daily Report Every Minute

[Timer]
OnCalendar=*-*-* *:*:00
Persistent=true
Unit=daily-report.service

[Install]
WantedBy=timers.target
```

Save and exit.

## STEP 11: RELOAD SYSTEMD

Run:

```bash
sudo systemctl daemon-reload
```

This reloads the systemd configuration files.

## STEP 12: ENABLE AND START THE TIMER

Run:

```bash
sudo systemctl enable --now daily-report.timer
```

This enables the timer and starts it immediately.

## STEP 13: VERIFY THE TIMER

Run:

```bash
systemctl list-timers
```

The output displays the scheduled systemd timers.

## STEP 14: EXECUTE THE SERVICE MANUALLY

Run:

```bash
sudo systemctl start daily-report.service
```

Check service status:

```bash
sudo systemctl status daily-report.service
```

A successful execution may show `status=0/SUCCESS`.

## STEP 15: VIEW SERVICE LOGS

Run:

```bash
journalctl -u daily-report.service
```

This displays the execution logs of the service.

---

# PART 5 – STOP AUTOMATION

## STEP 16: STOP THE SYSTEMD TIMER

Run:

```bash
sudo systemctl disable --now daily-report.timer
```

This disables and stops the timer.

## STEP 17: REMOVE THE CRON JOB

Open:

```bash
crontab -e
```

Delete only the Cron line added for this experiment.

Save and exit.

Verify:

```bash
crontab -l
```

---

# PART 6 – FINAL VERIFICATION

Verify the following:

1. New project directory created.
2. Shell script created successfully.
3. Execution permission provided.
4. Shell script executed successfully.
5. Cron job scheduled.
6. Report log generated.
7. Cron service verified.
8. systemd service created.
9. systemd timer created and enabled.
10. Service execution verified.
11. Execution logs displayed.
12. Automation stopped after verification.

## EXPECTED OUTPUT

- Daily automation report displayed in the terminal.
- Cron job listed successfully.
- Report output stored in report.log.
- systemd timer displayed in the timer list.
- Service execution completed successfully.
- Service logs displayed using journalctl.

## RESULT

Thus, job scheduling and automation were implemented successfully in Linux using Cron and systemd timers. The shell script was executed automatically, and the generated reports and service logs were verified.

---

# OPTIONAL COMMANDS FOR QUICK REVISION

| Command | Purpose |
|---|---|
| `pwd` | Display current directory |
| `mkdir folder` | Create directory |
| `cd folder` | Enter directory |
| `nano file.sh` | Create or edit a file |
| `chmod +x file.sh` | Give execution permission |
| `./file.sh` | Execute shell script |
| `crontab -e` | Edit Cron jobs |
| `crontab -l` | List Cron jobs |
| `cat report.log` | Display log file |
| `sudo systemctl status cron` | Check Cron service |
| `systemctl list-timers` | List systemd timers |
| `journalctl -u daily-report.service` | Display service logs |

## IMPORTANT

Cron and systemd timers are two separate scheduling methods.

Cron schedules commands directly using crontab.

systemd uses a service file to define the task and a timer file to schedule it.
