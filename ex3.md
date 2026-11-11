EXPERIMENT – AGILE PROJECT MANAGEMENT USING GITHUB FOR SERVER MONITORING APPLICATION
AIM

To implement Agile project management using GitHub Projects by creating a project board for a Server Monitoring Application, developing user stories for CPU, Memory, Disk, and Overall Server Health Monitoring, creating GitHub Issues, organizing tasks into Backlog, To Do, In Progress, and Done, and linking Git commits with GitHub Issues.

SOFTWARE REQUIREMENTS
Ubuntu Linux
Git
GitHub Account
GitHub Repository
GitHub Projects
PROJECT DESCRIPTION

A software company is developing a Server Monitoring Application to monitor server resources and identify performance problems.

The application includes:

CPU Monitoring – Monitor CPU utilization and identify high CPU usage.
Memory Monitoring – Monitor RAM utilization and identify memory shortages.
Disk Monitoring – Monitor disk space and identify low storage availability.
Overall Server Health – Display the overall health status of the server.
IMPORTANT

This experiment is completely independent.

Create:

A NEW GitHub repository.
A NEW GitHub Project Board.
NEW GitHub Issues.
A NEW local project folder.

Do not use any previous experiment's repository or files.

PART 1 – CREATE A NEW GITHUB REPOSITORY
STEP 1 – Open GitHub
Open https://github.com
Log in to your GitHub account.
Click the + icon at the top-right corner.
Select New repository.
STEP 2 – Create Repository

Enter:

Repository name:

server-monitoring-agile

Description:

Agile project management for CPU, Memory, Disk and Server Health Monitoring Application

Visibility: Public

Select Add a README file.

Click Create repository.

Your repository URL will be:

https://github.com/YOUR_USERNAME/server-monitoring-agile

Replace YOUR_USERNAME with your actual GitHub username.

PART 2 – CREATE A NEW AGILE PROJECT BOARD
STEP 3 – Create GitHub Project
Open your GitHub account.
Click your profile picture.
Select Your projects.
Click New project.
Select Board.
Enter the project name:

Server Monitoring Agile Project Board

Click Create project.
STEP 4 – Configure Status Columns

Configure the following four statuses:

Backlog
To Do
In Progress
Done

If the required statuses are unavailable:

Open the Status field dropdown.
Select Edit field.
Add the missing status options.
Save the changes.

Your board must contain four columns:

Backlog	To Do	In Progress	Done
Future Tasks	Ready Tasks	Active Tasks	Completed Tasks
PART 3 – CREATE USER STORIES AND GITHUB ISSUES
STEP 5 – Open the Repository

Open:

https://github.com/YOUR_USERNAME/server-monitoring-agile

Click Issues.
Click New issue.

If Issues is unavailable, open repository Settings and enable Issues under Features.

Create the following 10 Issues.

STEP 6 – CREATE ISSUE 1: CPU MONITORING

Title:

Implement CPU Usage Monitoring

Description:

text
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


Click Create issue.

STEP 7 – CREATE ISSUE 2: CPU ALERT SYSTEM

Title:

Develop CPU Usage Alert System

Description:

text
USER STORY:

As a system administrator,
I want to receive alerts when CPU utilization becomes too high,
so that I can take action before server performance is affected.

TASKS:

1. Define a CPU usage threshold.
2. Compare current CPU usage with the threshold.
3. Identify excessive CPU utilization.
4. Generate alerts when the threshold is exceeded.
5. Test CPU alert functionality.

ACCEPTANCE CRITERIA:

1. CPU threshold must be configurable.
2. An alert must be generated when CPU usage exceeds the threshold.
3. Normal CPU usage must not generate unnecessary alerts.

MODULE: CPU MONITORING
PRIORITY: HIGH


Click Create issue.

STEP 8 – CREATE ISSUE 3: MEMORY MONITORING

Title:

Implement Memory Usage Monitoring

Description:

text
USER STORY:

As a system administrator,
I want to monitor RAM utilization,
so that I can identify memory shortages and prevent server crashes.

TASKS:

1. Collect memory utilization information.
2. Identify total RAM capacity.
3. Identify used memory.
4. Calculate available memory.
5. Display memory utilization percentage.
6. Verify memory monitoring functionality.

ACCEPTANCE CRITERIA:

1. Total memory must be displayed.
2. Used memory must be displayed.
3. Available memory must be displayed.
4. Memory utilization must be displayed as a percentage.

MODULE: MEMORY MONITORING
PRIORITY: HIGH


Click Create issue.

STEP 9 – CREATE ISSUE 4: MEMORY ALERT SYSTEM

Title:

Develop Memory Usage Alert System

Description:

text
USER STORY:

As a system administrator,
I want to receive alerts when memory utilization becomes too high,
so that I can prevent memory-related server problems.

TASKS:

1. Define a memory usage threshold.
2. Compare current memory usage with the threshold.
3. Identify memory shortages.
4. Generate alerts when memory usage exceeds the threshold.
5. Test memory alert functionality.

ACCEPTANCE CRITERIA:

1. Memory threshold must be configurable.
2. Alerts must be generated when memory usage exceeds the threshold.
3. Insufficient available memory must be identifiable.

MODULE: MEMORY MONITORING
PRIORITY: HIGH


Click Create issue.

STEP 10 – CREATE ISSUE 5: DISK MONITORING

Title:

Implement Disk Space Monitoring

Description:

text
USER STORY:

As a system administrator,
I want to monitor disk space utilization,
so that I can identify storage problems before the disk becomes full.

TASKS:

1. Collect disk utilization information.
2. Identify total disk capacity.
3. Identify used disk space.
4. Calculate available disk space.
5. Display disk usage percentage.
6. Verify disk monitoring functionality.

ACCEPTANCE CRITERIA:

1. Total disk space must be displayed.
2. Used disk space must be displayed.
3. Available disk space must be displayed.
4. Disk utilization must be displayed as a percentage.

MODULE: DISK MONITORING
PRIORITY: HIGH


Click Create issue.

STEP 11 – CREATE ISSUE 6: DISK ALERT SYSTEM

Title:

Develop Disk Space Alert System

Description:
give full instruction to paste in .md file in gitube
text
USER STORY:

As a system administrator,
I want to receive alerts when disk space becomes low,
so that I can prevent storage-related server failures.

TASKS:

1. Define a disk usage threshold.
2. Compare current disk usage with the threshold.
3. Identify low disk space.
4. Generate alerts when disk usage exceeds the threshold.
5. Test disk alert functionality.

ACCEPTANCE CRITERIA:

1. Disk threshold must be configurable.
2. Alerts must be generated when disk usage exceeds the threshold.
3. Insufficient available storage must be identifiable.

MODULE: DISK MONITORING
PRIORITY: HIGH


Click Create issue.

STEP 12 – CREATE ISSUE 7: OVERALL SERVER HEALTH DASHBOARD

Title:

Develop Overall Server Health Dashboard

Description:

text
USER STORY:

As a system administrator,
I want to view the overall server health status,
so that I can quickly identify server resource problems.

TASKS:

1. Collect CPU monitoring information.
2. Collect memory monitoring information.
3. Collect disk monitoring information.
4. Combine CPU, memory and disk information.
5. Display overall server health status.
6. Identify healthy and unhealthy server conditions.
7. Test the overall health dashboard.

ACCEPTANCE CRITERIA:

1. CPU usage must be displayed.
2. Memory usage must be displayed.
3. Disk usage must be displayed.
4. Overall server health must be displayed.
5. Resource-related problems must be identifiable.

MODULE: SERVER HEALTH DASHBOARD
PRIORITY: HIGH


Click Create issue.

STEP 13 – CREATE ISSUE 8: RESOURCE USAGE REPORTS

Title:

Generate Server Resource Usage Reports

Description:

text
USER STORY:

As a system administrator,
I want to generate server resource usage reports,
so that I can analyze CPU, memory and disk utilization.

TASKS:

1. Collect CPU usage information.
2. Collect memory usage information.
3. Collect disk usage information.
4. Generate resource utilization reports.
5. Display report information.
6. Verify report generation.

ACCEPTANCE CRITERIA:

1. Reports must include CPU utilization.
2. Reports must include memory utilization.
3. Reports must include disk utilization.
4. Reports must provide readable resource information.

MODULE: REPORTING
PRIORITY: MEDIUM


Click Create issue.

STEP 14 – CREATE ISSUE 9: RESOURCE THRESHOLD CONFIGURATION

Title:

Configure CPU Memory and Disk Thresholds

Description:

text
USER STORY:

As a system administrator,
I want to configure CPU, memory and disk usage thresholds,
so that I can customize when resource alerts are generated.

TASKS:

1. Configure CPU usage threshold.
2. Configure memory usage threshold.
3. Configure disk usage threshold.
4. Store threshold configurations.
5. Verify threshold settings.

ACCEPTANCE CRITERIA:

1. CPU threshold must be configurable.
2. Memory threshold must be configurable.
3. Disk threshold must be configurable.
4. Configured thresholds must be used by the alert system.

MODULE: CONFIGURATION
PRIORITY: MEDIUM


Click Create issue.

STEP 15 – CREATE ISSUE 10: APPLICATION TESTING

Title:

Perform Server Monitoring Application Testing

Description:

text
USER STORY:

As a software tester,
I want to test CPU, memory and disk monitoring functionality,
so that I can ensure the application provides accurate server information.

TASKS:

1. Test CPU utilization monitoring.
2. Test memory utilization monitoring.
3. Test disk space monitoring.
4. Test CPU alerts.
5. Test memory alerts.
6. Test disk alerts.
7. Test overall server health dashboard.
8. Verify application functionality.

ACCEPTANCE CRITERIA:

1. CPU monitoring must work correctly.
2. Memory monitoring must work correctly.
3. Disk monitoring must work correctly.
4. Alerts must be generated correctly.
5. Overall server health must be displayed correctly.

MODULE: TESTING
PRIORITY: HIGH


Click Create issue.

PART 4 – CONNECT ISSUES TO THE AGILE PROJECT BOARD
STEP 16 – Add Issues to Project

For each Issue:

Open the Issue.
Find Projects on the right side.
Click the project selection option.
Select Server Monitoring Agile Project Board.
Repeat for all 10 Issues.

Alternatively:

Open the Project Board.
Click Add item.
Search for your repository Issues.
Select the Issues to add.

Verify that all 10 Issues appear on the board.

PART 5 – ORGANIZE TASKS INTO AGILE STATUS COLUMNS
STEP 17 – Assign Initial Statuses

Use the following table:

Issue	Task Name	Status
1	Implement CPU Usage Monitoring	To Do
2	Develop CPU Usage Alert System	Backlog
3	Implement Memory Usage Monitoring	In Progress
4	Develop Memory Usage Alert System	Backlog
5	Implement Disk Space Monitoring	To Do
6	Develop Disk Space Alert System	Backlog
7	Develop Overall Server Health Dashboard	In Progress
8	Generate Server Resource Usage Reports	Backlog
9	Configure CPU Memory and Disk Thresholds	To Do
10	Perform Server Monitoring Application Testing	Done

These are demonstration statuses. They do not mean that the corresponding features have already been implemented.

STEP 18 – Move Issues into Columns
Open the Project Board.
Find each Issue card.
Drag and drop it into the appropriate column.
Verify that the Issues appear under the correct statuses.

Your initial Agile board should look like this:

BACKLOG:

Develop CPU Usage Alert System
Develop Memory Usage Alert System
Develop Disk Space Alert System
Generate Server Resource Usage Reports

TO DO:

Implement CPU Usage Monitoring
Implement Disk Space Monitoring
Configure CPU Memory and Disk Thresholds

IN PROGRESS:

Implement Memory Usage Monitoring
Develop Overall Server Health Dashboard

DONE:

Perform Server Monitoring Application Testing
PART 6 – CREATE A NEW LOCAL PROJECT IN UBUNTU
STEP 19 – Open Ubuntu Terminal

Press:

Ctrl + Alt + T

Run:

bash
cd ~

STEP 20 – Clone the GitHub Repository

Run:

bash
git clone https://github.com/YOUR_USERNAME/server-monitoring-agile.git


Replace YOUR_USERNAME with your GitHub username.

Enter the project folder:

bash
cd server-monitoring-agile
