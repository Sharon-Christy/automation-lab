
# EXERCISE 3 – AGILE PROJECT MANAGEMENT WITH GIT

**Subject:** Open Source Systems, Agile Tools and Prompt Engineering  
**Name:** Sharon Christy R  
**Register Number:** 26120159

## AIM

To create and manage an Agile project using GitHub Projects, create user stories and issues, track task progress using different statuses, map scheduled jobs to Agile tasks, and link Git commits with issues to maintain project traceability.

## SOFTWARE REQUIREMENTS

1. Ubuntu Linux
2. Git
3. GitHub Account
4. GitHub Repository
5. GitHub Projects

# PROCEDURE

## STEP 1: OPEN GITHUB

1. Open https://github.com
2. Log in to your GitHub account.
3. Click your profile picture.
4. Select Your projects.
5. Click New project.
6. Select Board as the project view.
7. Enter the project name:

Software Development Task Management

8. Click Create project.

## STEP 2: CONFIGURE PROJECT STATUS

Create or verify the following status options:

1. Backlog
2. To Do
3. In Progress
4. Done

To add Backlog:

1. Open the Status field menu.
2. Select Edit field.
3. Add a new option named Backlog.
4. Save the changes.

The board is now ready to track Agile tasks.

## STEP 3: CREATE A USER STORY

1. Open the GitHub repository.
2. Click Issues.
3. Select New issue.

Enter the following:

Title:
Automate Daily Project Report

Description:

User Story:

As a software developer,
I want to generate daily project reports automatically,
so that the team can monitor project execution.

Tasks:
1. Create a Bash script.
2. Schedule the script using Cron.
3. Store execution results in a log file.
4. Upload results to GitHub.

4. Click Create issue.

## STEP 4: ADD ISSUE TO PROJECT BOARD

1. Open the newly created Issue.
2. Find Projects on the right side.
3. Select Software Development Task Management.
4. Open the Project Board.
5. Verify that the issue appears.

If the issue does not appear, use Add item in the project board and search for the issue.

## STEP 5: UPDATE TASK STATUS

Move the issue through the following statuses:

1. Backlog – Task is waiting for planning.
2. To Do – Task is ready to start.
3. In Progress – Developer is working on it.
4. Done – Task is successfully completed.

Change the Status field for each task.

## STEP 6: CREATE ADDITIONAL ISSUES

Create the following two additional issues.

ISSUE 2

Title:
Implement Automated Git Backup

Description:

User Story:

As a software developer,
I want to automatically commit and push project files,
so that project changes are safely maintained in GitHub.

Tasks:
1. Configure Git repository.
2. Create an automation script.
3. Automatically commit changes.
4. Push changes to GitHub.

ISSUE 3

Title:
Validate Scripts Before Commit

Description:

User Story:

As a team leader,
I want scripts to be validated before committing,
so that incorrect files are not saved in the repository.

Tasks:
1. Create a pre-commit hook.
2. Validate project files.
3. Display validation results.
4. Allow or reject the commit.

Add both issues to the Software Development Task Management project.

## STEP 7: MAP CRON JOBS TO AGILE ISSUES

Create the following mapping:

| Scheduled Task | Corresponding Issue |
|----------------|---------------------|
| Generate daily report | Issue #1 |
| Automatically push backup | Issue #2 |
| Validate project scripts | Issue #3 |

Explanation:

1. Cron executes the scheduled automation script.
2. The script generates the required output.
3. Git tracks the changes.
4. Commits are associated with the corresponding GitHub Issues.
5. The team monitors the progress using GitHub Projects.

## STEP 8: LINK GIT COMMITS WITH AGILE ISSUES

Open Ubuntu terminal.

Enter the project directory:

```bash
cd ~/automation_os
```

Generate a new report entry:

```bash
echo "Agile project integration completed: $(date)" >> report.log
```

Add the modified file:

```bash
git add report.log
```

Commit the change using the actual Issue number.

Example, if the Issue number is 1:

```bash
git commit -m "Update daily report for #1"
```

Push the changes:

```bash
git push origin main
```

Verify the commit:

```bash
git log --oneline
```

Open the GitHub repository and verify the commit.

The issue reference in the commit message helps connect the code change with the corresponding Agile task.

To automatically close an issue when the commit reaches the default branch, use a closing keyword:

```bash
git commit -m "Complete daily report task, fixes #1"
```

## STEP 9: VERIFY PROJECT PROGRESS

Open GitHub Projects.

Verify:

1. All three Issues are available.
2. Each Issue is linked to the Project.
3. Statuses are updated correctly.
4. Commits reference the corresponding Issues.
5. Completed tasks are moved to Done.

Note: GitHub Project status changes are manual in this basic implementation. Automatic status updates require additional API or workflow integration.

# IMPORTANT COMMANDS

```bash
cd ~/automation_os
git status
git add report.log
git commit -m "Update daily report for #1"
git push origin main
git log --oneline
```

# RESULT

Thus, an Agile project board was created using GitHub Projects. User stories and issues were created and linked to the project board. Task progress was monitored using Backlog, To Do, In Progress and Done statuses. Scheduled jobs were mapped to Agile issues, and Git commits were linked with corresponding issues to maintain project traceability.
