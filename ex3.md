
# EXPERIMENT 3 – AGILE PROJECT MANAGEMENT WITH GIT

## AIM

To implement Agile project management using GitHub Projects, create user stories and issues, track task progress, map scheduled jobs to Agile tasks, and link Git commits with GitHub Issues.

## SOFTWARE REQUIREMENTS

- Ubuntu Linux
- Git
- GitHub Account
- GitHub Projects

## IMPORTANT

This experiment is completely independent.

Create:
- A NEW GitHub repository
- A NEW GitHub Project Board
- NEW GitHub Issues
- A NEW local project folder

Do not use any previous experiment's repository or files.

---

# PART 1 – CREATE A NEW GITHUB REPOSITORY

## STEP 1: Open GitHub

1. Open https://github.com
2. Log in to your GitHub account.
3. Click the + icon at the top.
4. Select New repository.

## STEP 2: Create Repository

Enter:

Repository name:

`agile-project-lab`

Description:

`Agile project management using Git and GitHub Projects`

Visibility: Public

Select **Add a README file**.

Click **Create repository**.

Your NEW repository URL will be:

https://github.com/Sharon-Christy/agile-project-lab

---

# PART 2 – CREATE A NEW AGILE PROJECT BOARD

## STEP 3: Create GitHub Project

1. Click your GitHub profile picture.
2. Select Your projects.
3. Click New project.
4. Select Board.
5. Enter the name:

`Agile Software Development Management`

6. Click Create project.

## STEP 4: Configure Status Columns

Configure these statuses:

1. Backlog
2. To Do
3. In Progress
4. Done

If Backlog is missing:

1. Open the Status field menu.
2. Select Edit field.
3. Add Backlog.
4. Save changes.

---

# PART 3 – CREATE NEW AGILE ISSUES

## STEP 5: Open the New Repository

Open:

https://github.com/Sharon-Christy/agile-project-lab

Select Issues.

If Issues is unavailable, open repository Settings and enable Issues under Features.

## STEP 6: Create Issue 1

Click New issue.

Title:

`Develop Daily Report Generator`

Description:

```text
User Story:

As a project manager,
I want to generate daily progress reports,
so that I can monitor team activities.

Tasks:
1. Create a Bash script.
2. Generate a daily report.
3. Save the report in a log file.
4. Verify execution.
```

Click Create issue.

Remember the actual Issue number displayed by GitHub.

## STEP 7: Create Issue 2

Click New issue.

Title:

`Implement Scheduled Report Execution`

Description:

```text
User Story:

As a developer,
I want the report script to run automatically,
so that manual execution is not required.

Tasks:
1. Configure Cron.
2. Schedule daily execution.
3. Verify scheduled execution.
4. Check generated reports.
```

Click Create issue.

## STEP 8: Create Issue 3

Click New issue.

Title:

`Maintain Project Version History`

Description:

```text
User Story:

As a developer,
I want to track project changes using Git,
so that the development history is maintained.

Tasks:
1. Track source files.
2. Commit project changes.
3. Push changes to GitHub.
4. Link commits with issues.
```

Click Create issue.

---

# PART 4 – CONNECT ISSUES TO PROJECT BOARD

## STEP 9: Add Issues

1. Open Issue 1.
2. Find Projects on the right.
3. Select Agile Software Development Management.
4. Repeat for Issue 2 and Issue 3.

Alternatively, open the Project Board and use Add item to find the repository Issues.

Verify that all three Issues appear.

## STEP 10: Update Agile Status

Use these statuses:

| Task | Status |
|---|---|
| Develop Daily Report Generator | In Progress |
| Implement Scheduled Report Execution | To Do |
| Maintain Project Version History | Backlog |

After completing a task, move it to Done.

---

# PART 5 – CREATE NEW PROJECT IN UBUNTU

## STEP 11: Open Ubuntu Terminal

Go to home directory:

```bash
cd ~
```

Clone the NEW repository:

```bash
git clone https://github.com/Sharon-Christy/agile-project-lab.git
```

Enter the folder:

```bash
cd agile-project-lab
```

Verify:

```bash
git status
```

## STEP 12: Configure Git Identity

Only if Git identity is not already configured:

```bash
git config --global user.name "Sharon Christy R"
git config --global user.email "YOUR_GITHUB_EMAIL"
```

Replace YOUR_GITHUB_EMAIL with your GitHub email.

## STEP 13: Create Daily Report Script

```bash
nano daily_report.sh
```

Paste:

```bash
#!/bin/bash

echo "AGILE PROJECT DAILY REPORT"
echo "--------------------------"
echo "Project: Agile Software Development"
echo "Task: Daily Report Generation"
echo "Status: Completed"
echo "Date: $(date)"
```

Save:

1. Ctrl + O
2. Enter
3. Ctrl + X

## STEP 14: Give Execution Permission

```bash
chmod +x daily_report.sh
```

## STEP 15: Execute Script

```bash
./daily_report.sh
```

Expected output:

```text
AGILE PROJECT DAILY REPORT
--------------------------
Project: Agile Software Development
Task: Daily Report Generation
Status: Completed
Date: [current date and time]
```

## STEP 16: Generate Report Log

```bash
./daily_report.sh >> report.log
```

Verify:

```bash
cat report.log
```

---

# PART 6 – MAP SCHEDULED JOBS TO AGILE ISSUES

## STEP 17: Create Cron Schedule

Open Cron editor:

```bash
crontab -e
```

Choose Nano if asked.

Add this line:

```cron
* * * * * /bin/bash /home/$USER/agile-project-lab/daily_report.sh >> /home/$USER/agile-project-lab/report.log 2>&1
```

IMPORTANT: Cron does not reliably expand $USER in paths.

Therefore, replace the line above with your actual Ubuntu username. For example:

```cron
* * * * * /bin/bash /home/sharon_christy_r/agile-project-lab/daily_report.sh >> /home/sharon_christy_r/agile-project-lab/report.log 2>&1
```

Save and exit.

Check:

```bash
crontab -l
```

Wait approximately one minute.

Check:

```bash
cat report.log
```

The report should contain new execution entries if Cron is running.

If necessary:

```bash
sudo systemctl start cron
```

## STEP 18: Map Jobs to Issues

| Scheduled Activity | Agile Issue |
|---|---|
| Generate daily report | Develop Daily Report Generator |
| Schedule report with Cron | Implement Scheduled Report Execution |
| Track project changes | Maintain Project Version History |

Update the corresponding Issue status manually after verifying the activity.

---

# PART 7 – LINK GIT COMMITS WITH AGILE ISSUES

## STEP 19: Check Git Status

```bash
git status
```

## STEP 20: Stage Project Files

```bash
git add daily_report.sh report.log
```

## STEP 21: Commit with Issue Reference

Use the actual Issue number for "Develop Daily Report Generator".

If the Issue number is 1:

```bash
git commit -m "Implement daily report generator refs #1"
```

The `refs #1` text links the commit to Issue #1 without automatically closing it.

## STEP 22: Push to GitHub

```bash
git push origin main
```

For HTTPS authentication, use an authorized GitHub Personal Access Token or browser-based login, not your normal GitHub password.

## STEP 23: Verify Commit History

```bash
git log --oneline
```

Open the GitHub repository.

1. Click Commits.
2. Open the latest commit.
3. Open Issue 1.
4. Verify that the commit is referenced in the Issue timeline.

## STEP 24: Update Issue Status

Open the Project Board.

Move "Develop Daily Report Generator" to Done.

Move "Implement Scheduled Report Execution" to Done after verifying the Cron job.

Move "Maintain Project Version History" to Done after verifying the Git push.

All three Issues should now appear in Done.

---

# PART 8 – FINAL VERIFICATION

Verify:

1. New repository created.
2. New GitHub Project Board created.
3. Three new Issues created.
4. Issues connected to the Project Board.
5. Task statuses updated.
6. Daily report script executed.
7. Cron job configured and verified.
8. Scheduled jobs mapped to Issues.
9. Git commit linked with an Issue.
10. Changes pushed successfully to GitHub.

## EXPECTED OUTPUT

- A GitHub Project Board with Agile statuses.
- Three GitHub Issues representing user stories.
- A working Bash report generator.
- A scheduled Cron job.
- A report log file.
- A Git commit referencing the appropriate Issue.
- Completed tasks displayed in the Done status.

## RESULT

Thus, Agile project management was implemented using a new GitHub repository and GitHub Projects. User stories and Issues were created, tasks were tracked through Agile status columns, a scheduled reporting job was mapped to the corresponding Issues, and Git commits were linked to Agile tasks successfully.

## CLEANUP (OPTIONAL)

To stop the one-minute Cron job after the practical:

```bash
crontab -e
```

Delete only the line added for this experiment, then save and exit.

Verify:

```bash
crontab -l
```
