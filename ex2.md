# EXPERIMENT – AGILE PROJECT MANAGEMENT USING GITHUB FOR SERVER MONITORING APPLICATION

## AIM

To implement Agile project management using GitHub Projects by creating an Agile Project Board for a Server Monitoring Application, developing user stories for CPU, Memory, Disk and Overall Server Health Monitoring, creating GitHub Issues, organizing tasks into Backlog, To Do, In Progress and Done, and linking Git commits with GitHub Issues.

## SOFTWARE REQUIREMENTS

- Ubuntu Linux
- Git
- GitHub Account
- GitHub Repository
- GitHub Projects

## PROJECT DESCRIPTION

A software company is developing a Server Monitoring Application to monitor server resources and identify performance problems.

The application includes:

1. CPU Monitoring – Monitor CPU utilization and identify high CPU usage.
2. Memory Monitoring – Monitor RAM utilization and identify memory shortages.
3. Disk Monitoring – Monitor disk space and identify low storage availability.
4. Overall Server Health – Display the overall health status of the server.

## IMPORTANT

This experiment is completely independent.

Create:

- A NEW GitHub repository.
- A NEW GitHub Project Board.
- NEW GitHub Issues.
- A NEW local project folder.

Do not use any previous experiment's repository or files.

---

# PART 1 – CREATE A NEW GITHUB REPOSITORY

## STEP 1 – Open GitHub

1. Open https://github.com
2. Log in to your GitHub account.
3. Click the + icon at the top-right corner.
4. Select New repository.

## STEP 2 – Create Repository

Enter the following details:

**Repository name:**

`server-monitoring-agile`

**Description:**

`Agile project management for CPU, Memory, Disk and Server Health Monitoring Application`

**Visibility:** Public

Select Add a README file.

Click Create repository.

Your repository URL will be:

`https://github.com/YOUR_USERNAME/server-monitoring-agile`

Replace YOUR_USERNAME with your actual GitHub username.

---

# PART 2 – CREATE A NEW AGILE PROJECT BOARD

## STEP 3 – Create GitHub Project

1. Open your GitHub account.
2. Click your profile picture.
3. Select Your projects.
4. Click New project.
5. Select Board.
6. Enter the project name:

`Server Monitoring Agile Project Board`

7. Click Create project.

## STEP 4 – Configure Status Columns

Configure the following four statuses:

1. Backlog
2. To Do
3. In Progress
4. Done

If the required statuses are unavailable:

1. Open the Status field dropdown.
2. Select Edit field.
3. Add the missing status options.
4. Save the changes.

Your board must contain four columns:

| Backlog | To Do | In Progress | Done |
|---|---|---|---|
| Future Tasks | Ready Tasks | Active Tasks | Completed Tasks |

---

# PART 3 – CREATE USER STORIES AND GITHUB ISSUES

## STEP 5 – Open the Repository

Open:

`https://github.com/YOUR_USERNAME/server-monitoring-agile`

1. Click Issues.
2. Click New issue.

If Issues is unavailable, open repository Settings and enable Issues under Features.

Create the following 10 Issues.

## STEP 6 – CREATE ISSUE 1: CPU MONITORING

**Title:**

`Implement CPU Usage Monitoring`

**Description:**

```text
USER STORY:

As a system administrator,
I want to monitor CPU utilization,
so that I can identify high CPU usage and prevent server performance problems.

TASKS:

1. Collect CPU utilization information.
2. Identify CPU usage percentage.
3. Display CPU usage.
4. Identify high CPU utilization.
5. Verify CPU monitoring functionality.

ACCEPTANCE CRITERIA:

1. CPU utilization must be displayed as a percentage.
2. High CPU usage must be identifiable.
3. CPU information must be available to administrators.

MODULE: CPU MONITORING
PRIORITY: HIGH
