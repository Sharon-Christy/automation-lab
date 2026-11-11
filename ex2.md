
# EXERCISE 2 – GIT AND GITHUB INTEGRATION

**Subject:** Open Source Systems, Agile Tools and Prompt Engineering  
**Name:** Sharon Christy R  
**Register Number:** 26120159

## AIM
To initialize Git repositories, track changes, commit files, automatically commit job outputs using Bash scripts, push changes to GitHub, manage branches, and implement Git hooks to validate project files.

## A. INITIALIZE GIT REPOSITORY

### Step 1: Create a project folder
```bash
mkdir git_lab
cd git_lab
```

### Step 2: Create a sample script
```bash
nano project.sh
```

Enter:
```bash
#!/bin/bash
echo "Software Development Project"
echo "Project Status: Successful"
echo "Execution Date: $(date)"
```

Save: Ctrl+O, Enter, Ctrl+X.

### Step 3: Give execution permission and run
```bash
chmod +x project.sh
./project.sh
```

### Step 4: Configure Git identity
```bash
git config --global user.name "Sharon Christy R"
git config --global user.email "YOUR_GITHUB_EMAIL"
```

### Step 5: Initialize Git
```bash
git init
git status
```

### Step 6: Add files
```bash
git add .
git status
```

### Step 7: Commit changes
```bash
git commit -m "Initial project commit"
```

### Step 8: View commit history
```bash
git log --oneline
```

## B. CONNECT AND PUSH TO GITHUB

1. Open https://github.com
2. Click + → New repository.
3. Repository name: git-lab
4. Select Public.
5. Do not initialize with README.
6. Click Create repository.

### Step 9: Connect remote repository

Replace YOUR_USERNAME with the GitHub username and use the actual repository URL.

```bash
git remote add origin https://github.com/YOUR_USERNAME/git-lab.git
git remote -v
```

### Step 10: Push to GitHub
```bash
git branch -M main
git push -u origin main
```

If authentication is requested:
- Username: GitHub username.
- Password prompt: Personal Access Token (PAT), not normal GitHub password.

## C. BRANCH MANAGEMENT

### Step 11: Create a branch
```bash
git branch feature-report
git branch
```

### Step 12: Switch to the branch
```bash
git switch feature-report
```

### Step 13: Modify the project
```bash
nano project.sh
```

Add:
```bash
echo "New report feature added"
```

### Step 14: Commit the change
```bash
git add project.sh
git commit -m "Add report feature"
```

### Step 15: Push the branch
```bash
git push -u origin feature-report
```

### Step 16: Switch to main
```bash
git switch main
```

### Step 17: Merge the feature branch
```bash
git merge feature-report
```

### Step 18: Push updated main
```bash
git push origin main
```

### Step 19: Verify branches
```bash
git branch -a
git log --oneline --graph --all
```

## D. AUTOMATIC GIT COMMIT USING BASH

### Step 20: Create a log file
```bash
echo "Automation started: $(date)" >> report.log
```

### Step 21: Create an automation script
```bash
nano auto_commit.sh
```

Enter:
```bash
#!/bin/bash
set -e

cd /home/sharon_christy_r/git_lab

git add report.log

if git diff --cached --quiet; then
    echo "No changes to commit"
    exit 0
fi

git commit -m "Automated report update"
git push origin main

echo "Git automation completed successfully"
```

Use the correct project path and ensure you are working on main.

### Step 22: Give execution permission
```bash
chmod +x auto_commit.sh
```

### Step 23: Generate a new log entry
```bash
echo "New automated execution: $(date)" >> report.log
```

### Step 24: Run automation
```bash
./auto_commit.sh
```

Expected: Commit created and changes pushed to GitHub.

## E. GIT HOOKS

Git hooks automatically execute scripts during Git operations.

- Pre-commit: Executes before a commit.
- Post-commit: Executes after a successful commit.

### Step 25: Create pre-commit hook
```bash
nano .git/hooks/pre-commit
```

Enter:
```bash
#!/bin/bash

echo "Validating project files..."

if [ -f project.sh ]; then
    echo "Validation successful"
    exit 0
else
    echo "Error: project.sh not found"
    exit 1
fi
```

### Step 26: Give permission
```bash
chmod +x .git/hooks/pre-commit
```

### Step 27: Create post-commit hook
```bash
nano .git/hooks/post-commit
```

Enter:
```bash
#!/bin/bash

echo "Commit completed successfully!"
echo "Project changes saved in Git."
```

### Step 28: Give permission
```bash
chmod +x .git/hooks/post-commit
```

### Step 29: Test both hooks
```bash
echo "Git hook testing: $(date)" >> report.log
git add report.log
git commit -m "Test Git hooks"
```

Expected:
```text
Validating project files...
Validation successful
Commit completed successfully!
Project changes saved in Git.
```

## F. IMPORTANT VERIFICATION COMMANDS

```bash
git status
git log --oneline
git branch -a
git remote -v
git config --global --list
```

## RESULT

Thus, Git repository initialization, version tracking, automated commits, GitHub integration, branch management, and Git hooks were implemented and verified successfully.
