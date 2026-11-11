
# EXPERIMENT 3 – AGILE PROJECT MANAGEMENT WITH GIT

**Subject:** Open Source Systems, Agile Tools and Prompt Engineering  
**Name:** Sharon Christy R  
**Register Number:** 26120159

## AIM

To implement Agile project management using GitHub Projects by creating user stories, managing issues, tracking task progress, mapping scheduled jobs to issues, and linking Git commits with Agile tasks.

## SOFTWARE REQUIREMENTS

- Ubuntu Linux
- Git
- GitHub Account
- GitHub Repository
- GitHub Projects

## PROCEDURE

### STEP 1: OPEN GITHUB

1. Open https://github.com
2. Log in using your GitHub account.
3. Open your profile.
4. Select **Your projects**.

### STEP 2: CREATE A NEW PROJECT BOARD

1. Click **New project**.
2. Select **Board**.
3. Enter the project name:

   `Software Development Task Management`

4. Click **Create project**.

This creates a new Agile Project Board.

### STEP 3: CONFIGURE PROJECT STATUS

Configure the following status options:

1. Backlog
2. To Do
3. In Progress
4. Done

If Backlog is not available:

1. Open the Status field menu.
2. Select Edit field.
3. Add a new option named Backlog.
4. Save the changes.

### STEP 4: OPEN THE GITHUB REPOSITORY

Open the existing repository:

https://github.com/Sharon-Christy/automation-lab

The repository is used to create and track the Issues associated with the new Agile Project.

### STEP 5: CREATE ISSUE 1

1. Open the **Issues** tab.
2. Click **New issue**.
3. Enter the following details.

**Title:**

`Automate Daily Project Report`

**Description:**

As a software developer, I want to generate daily project reports automatically, so that the team can monitor project execution.

Tasks:
1. Create a report generation script.
2. Schedule the script using Cron.
3. Store execution results in a log file.
4. Track the generated report.

Click **Create issue**.

### STEP 6: CREATE ISSUE 2

Click **New issue**.

**Title:**

`Implement Automated Git Backup`

**Description:**

As a software developer, I want to automatically commit and push project files, so that project changes are safely maintained.

Tasks:
1. Initialize Git repository.
2. Track project files.
3. Automatically commit changes.
4. Push changes to GitHub.

Click **Create issue**.

### STEP 7: CREATE ISSUE 3

Click **New issue**.

**Title:**

`Validate Project Scripts`

**Description:**

As a team leader, I want project scripts to be validated, so that incorrect files are not committed.

Tasks:
1. Create a pre-commit hook.
2. Validate project files.
3. Display validation results.
4. Allow or reject commits based on validation.

Click **Create issue**.

### STEP 8: ADD ISSUES TO THE PROJECT BOARD

1. Open the first Issue.
2. Find the Projects section on the right side.
3. Select `Software Development Task Management`.
4. Repeat the same process for the remaining Issues.

Alternatively, open the Project Board, click Add item, and search for the Issues.

Verify that all three Issues appear on the Project Board.

### STEP 9: UPDATE TASK STATUS

Move the Issues through the following stages:

Backlog → To Do → In Progress → Done

Example:

| Issue | Initial Status | Updated Status |
|---|---|---|
| Automate Daily Project Report | Backlog | Done |
| Implement Automated Git Backup | To Do | In Progress |
| Validate Project Scripts | Backlog | To Do |

Update the Status field directly from the Project Board.

### STEP 10: MAP SCHEDULED JOBS TO AGILE ISSUES

Map the scheduled jobs to their corresponding Issues.

| Scheduled Job | GitHub Issue |
|---|---|
| Generate daily project report | Issue 1 |
| Automatically back up Git files | Issue 2 |
| Validate project scripts | Issue 3 |

This mapping connects automation activities with Agile tasks and helps track their progress.

### STEP 11: CLONE THE REPOSITORY IN UBUNTU

Open Ubuntu terminal.

Create a separate local working copy:

```bash
cd ~
git clone https://github.com/Sharon-Christy/automation-lab.git exercise3_lab
```

Enter the new directory:

```bash
cd exercise3_lab
```

Configure Git identity if required:

```bash
git config --global user.name "Sharon Christy R"
git config --global user.email "YOUR_GITHUB_EMAIL"
```

### STEP 12: CREATE AN AGILE TASK FILE

Create a file:

```bash
nano agile_task.txt
```

Enter the following content:

```text
Project: Software Development
Task: Automate Daily Project Report
Issue: #1
Status: Completed
```

Save the file:

- Press Ctrl + O.
- Press Enter.
- Press Ctrl + X.

### STEP 13: ADD THE FILE TO GIT

```bash
git add agile_task.txt
```

This stages the new file for committing.

### STEP 14: COMMIT THE CHANGES WITH ISSUE NUMBER

```bash
git commit -m "Complete daily report task #1"
```

Replace `#1` with the actual Issue number if it is different.

The Issue number helps GitHub associate the commit with the corresponding Issue.

### STEP 15: PUSH CHANGES TO GITHUB

```bash
git push origin main
```

This uploads the committed changes to the GitHub repository.

If GitHub asks for HTTPS authentication, use an authorized Personal Access Token or browser-based authentication, not the normal account password.

### STEP 16: VERIFY THE COMMIT

Execute:

```bash
git log --oneline
```

Open the GitHub repository and verify the latest commit.

Open the corresponding Issue and check its timeline for the commit reference.

**Note:** Mentioning an Issue number creates a reference. To automatically close an Issue when a commit is merged into the default branch, use a closing keyword such as `Closes #1`.

### STEP 17: FINAL VERIFICATION

Verify the following:

1. A new Agile Project Board has been created.
2. Three new Issues have been created.
3. All Issues have been added to the Project Board.
4. Task statuses have been updated.
5. Scheduled jobs have been mapped to Issues.
6. Git commits have been linked to the corresponding Issues.

## RESULT

Thus, Agile project management was implemented successfully using GitHub Projects and Git. A new Project Board was created, user stories and Issues were added, task progress was tracked using different statuses, scheduled jobs were mapped to Agile Issues, and Git commits were associated with the corresponding tasks.
