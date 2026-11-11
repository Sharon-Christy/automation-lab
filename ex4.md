
# EXPERIMENT 4 – CI/CD PIPELINE AND PROMPT-BASED AUTOMATION

**Subject:** Open Source Systems, Agile Tools and Prompt Engineering  
**Name:** Sharon Christy R  
**Register Number:** 26120159

---

## AIM

To implement a Continuous Integration and Continuous Delivery (CI/CD) pipeline using GitHub Actions, automate Python program testing, generate success and failure reports, perform prompt-based analysis, and upload execution reports as workflow artifacts.

## SOFTWARE REQUIREMENTS

1. Ubuntu Linux
2. Git
3. GitHub Account
4. GitHub Repository
5. Python 3
6. GitHub Actions
7. YAML

## EXPERIMENT OVERVIEW

In this experiment, a Python program is created and uploaded to a new GitHub repository.

Whenever code changes are pushed to the main branch, GitHub Actions automatically:

1. Checks out the repository.
2. Sets up Python.
3. Executes the Python testing program.
4. Identifies whether the test passes or fails.
5. Generates an execution report.
6. Performs prompt-based analysis.
7. Uploads the generated reports as downloadable artifacts.

---

# PART 1 – CREATE A NEW GITHUB REPOSITORY

## STEP 1: OPEN GITHUB

1. Open https://github.com
2. Log in using your GitHub account.
3. Click the + icon at the top-right corner.
4. Select New repository.

## STEP 2: CREATE A NEW REPOSITORY

Enter the following details:

**Repository name:**

`cicd-prompt-automation-lab`

**Description:**

`CI/CD pipeline and prompt-based automation using GitHub Actions and Python`

**Visibility:** Public

Select:

- Add a README file

Click Create repository.

The new repository will be available at:

`https://github.com/Sharon-Christy/cicd-prompt-automation-lab`

NOTE:
This is a completely new repository. No previous experiment repository is required.

---

# PART 2 – CLONE THE REPOSITORY IN UBUNTU

## STEP 3: OPEN UBUNTU TERMINAL

Open Ubuntu terminal.

Move to the home directory:

```bash
cd ~
```

Clone the new public repository:

```bash
git clone https://github.com/Sharon-Christy/cicd-prompt-automation-lab.git
```

NOTE:
Since the repository is public, HTTPS cloning normally does not require a username, password or Personal Access Token.

Enter the repository directory:

```bash
cd cicd-prompt-automation-lab
```

Verify the current directory:

```bash
pwd
```

Expected path:

`/home/sharon_christy_r/cicd-prompt-automation-lab`

Check Git status:

```bash
git status
```

Expected output:

```text
On branch main
nothing to commit, working tree clean
```

---

# PART 3 – CONFIGURE GIT

## STEP 4: CONFIGURE GIT IDENTITY

Configure the Git username:

```bash
git config --global user.name "Sharon Christy R"
```

Configure the Git email:

```bash
git config --global user.email "YOUR_GITHUB_EMAIL"
```

Replace YOUR_GITHUB_EMAIL with your GitHub email address.

Verify the configuration:

```bash
git config --global --list
```

---

# PART 4 – CREATE THE PYTHON TESTING PROGRAM

## STEP 5: CREATE A PYTHON FILE

Create a new file:

```bash
nano test_project.py
```

Enter the following Python code:

```python
print("CI/CD PIPELINE - PROJECT TESTING")
print("--------------------------------")

# Perform a simple calculation
a = 10
b = 20

result = a + b

print("First Number:", a)
print("Second Number:", b)
print("Result:", result)

# Validate the result
if result == 30:
    print("TEST PASSED")
else:
    print("TEST FAILED")
    raise SystemExit(1)
```

Save the file:

1. Press Ctrl + O.
2. Press Enter.
3. Press Ctrl + X.

## STEP 6: EXECUTE THE PYTHON PROGRAM

Run:

```bash
python3 test_project.py
```

EXPECTED OUTPUT:

```text
CI/CD PIPELINE - PROJECT TESTING
--------------------------------
First Number: 10
Second Number: 20
Result: 30
TEST PASSED
```

The program performs addition and checks whether the result is equal to 30.

If the condition is true, the test passes.

If the condition is false, the program exits with an error status.

---

# PART 5 – CREATE THE GITHUB ACTIONS WORKFLOW

## STEP 7: CREATE THE WORKFLOW DIRECTORY

GitHub Actions workflow files must be stored inside:

`.github/workflows/`

Create the directory:

```bash
mkdir -p .github/workflows
```

## STEP 8: CREATE THE YAML WORKFLOW FILE

Create the file:

```bash
nano .github/workflows/ci.yml
```

Enter the following code:

```yaml
name: CI CD and Prompt Automation

on:
  push:
    branches:
      - main
  workflow_dispatch:

jobs:
  test:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout Repository
        uses: actions/checkout@v4

      - name: Set up Python
        uses: actions/setup-python@v5
        with:
          python-version: '3.10'

      - name: Run Project Test
        run: python test_project.py

      - name: Generate Success Report
        if: success()
        run: echo "All tests passed successfully" > report.txt

      - name: Generate Failure Report
        if: failure()
        run: echo "Project testing failed. Check workflow logs." > report.txt

      - name: Upload Execution Report
        if: always()
        uses: actions/upload-artifact@v4
        with:
          name: project-execution-report
          path: report.txt
```

Save the file.

### UNDERSTANDING THE YAML FILE

| YAML element | Purpose |
|---|---|
| name | Name of the workflow |
| on | Defines when the workflow runs |
| push | Runs when code is pushed |
| workflow_dispatch | Allows manual execution |
| jobs | Defines the jobs to perform |
| runs-on | Specifies the execution environment |
| steps | Defines individual workflow steps |
| actions/checkout | Checks out repository files |
| actions/setup-python | Sets up Python |
| run | Executes a command |
| success() | Checks whether previous steps succeeded |
| failure() | Checks whether a previous step failed |
| always() | Runs regardless of previous step outcome |
| upload-artifact | Stores generated files as artifacts |

---

# PART 6 – CREATE PROMPT-BASED AUTOMATION

## STEP 9: CREATE A PYTHON PROMPT ANALYSIS FILE

Create:

```bash
nano prompt_report.py
```

Enter:

```python
import os

print("PROMPT-BASED AUTOMATION REPORT")
print("--------------------------------")

# Read the execution report
if os.path.exists("report.txt"):
    with open("report.txt", "r") as file:
        result = file.read()
else:
    result = "No execution report found"

# Create a prompt template
prompt = f"""
You are a software testing assistant.

Analyse the following project execution result:

{result}

Your tasks:
1. Summarize the result.
2. Identify errors.
3. Suggest corrective actions.
"""

print("\nPROMPT:")
print(prompt)

# Analyse the execution result
if "passed" in result.lower() and "failed" not in result.lower():
    summary = "Project testing completed successfully."
    error = "No errors detected."
    action = "Continue with the next development stage."
else:
    summary = "Project testing requires attention."
    error = "Execution failed or report is missing."
    action = "Check the workflow logs and correct the errors."

# Generate the final analysis report
with open("actionable_report.txt", "w") as file:
    file.write("AUTOMATED PROJECT ANALYSIS\n")
    file.write(summary + "\n")
    file.write(error + "\n")
    file.write("Recommended Action: " + action + "\n")

print("\nREPORT GENERATED SUCCESSFULLY")
print(summary)
print(error)
print("Recommended Action:", action)
```

Save and exit.

## STEP 10: EXECUTE THE PROMPT PROGRAM LOCALLY

First, create a sample success report:

```bash
echo "All tests passed successfully" > report.txt
```

Execute:

```bash
python3 prompt_report.py
```

Check the generated report:

```bash
cat actionable_report.txt
```

EXPECTED OUTPUT:

```text
AUTOMATED PROJECT ANALYSIS
Project testing completed successfully.
No errors detected.
Recommended Action: Continue with the next development stage.
```

The Python program reads the execution report, creates a structured prompt template, analyses the result using conditions, and generates an actionable report.

NOTE:
This is a rule-based prompt automation demonstration. It does not connect to an external AI model or API.

---

# PART 7 – INTEGRATE PROMPT AUTOMATION INTO THE CI/CD PIPELINE

## STEP 11: UPDATE THE WORKFLOW FILE

Open the YAML file:

```bash
nano .github/workflows/ci.yml
```

Replace the existing content with the following complete workflow:

```yaml
name: CI CD and Prompt Automation

on:
  push:
    branches:
      - main
  workflow_dispatch:

jobs:
  test:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout Repository
        uses: actions/checkout@v4

      - name: Set up Python
        uses: actions/setup-python@v5
        with:
          python-version: '3.10'

      - name: Run Project Test
        run: python test_project.py

      - name: Generate Success Report
        if: success()
        run: echo "All tests passed successfully" > report.txt

      - name: Generate Failure Report
        if: failure()
        run: echo "Project testing failed. Check workflow logs." > report.txt

      - name: Run Prompt-Based Analysis
        if: always()
        run: python prompt_report.py

      - name: Upload Execution Reports
        if: always()
        uses: actions/upload-artifact@v4
        with:
          name: project-execution-reports
          path: |
            report.txt
            actionable_report.txt
```

Save the file.

This workflow performs:

1. Repository checkout.
2. Python setup.
3. Python testing.
4. Success or failure report generation.
5. Prompt-based analysis.
6. Uploading execution reports.

The prompt analysis and artifact upload steps use `always()` so that they can run even when the test fails.

---

# PART 8 – COMMIT AND PUSH THE PROJECT

## STEP 12: CHECK PROJECT STATUS

```bash
git status
```

The following files should be visible:

- test_project.py
- prompt_report.py
- .github/workflows/ci.yml

The locally generated report files may also appear.

## STEP 13: ADD PROJECT FILES

```bash
git add test_project.py prompt_report.py .github/workflows/ci.yml
```

## STEP 14: COMMIT CHANGES

```bash
git commit -m "Implement CI CD and prompt automation"
```

## STEP 15: PUSH TO GITHUB

```bash
git push origin main
```

NOTE:
Cloning a public repository does not require authentication. Pushing changes does require GitHub authentication. Use an authorized Personal Access Token or GitHub CLI/browser authentication if prompted. Never use your normal GitHub account password as the HTTPS Git password.

---

# PART 9 – VERIFY THE CI/CD PIPELINE

## STEP 16: OPEN GITHUB ACTIONS

1. Open the repository:

   `https://github.com/Sharon-Christy/cicd-prompt-automation-lab`

2. Click the Actions tab.
3. Select CI CD and Prompt Automation.
4. Open the latest workflow run.
5. Click the test job.
6. Inspect the execution steps.

EXPECTED SUCCESSFUL STEPS:

1. Checkout Repository – Success.
2. Set up Python – Success.
3. Run Project Test – Success.
4. Generate Success Report – Success.
5. Run Prompt-Based Analysis – Success.
6. Upload Execution Reports – Success.

A green check mark indicates successful execution.

---

# PART 10 – TEST THE FAILURE SCENARIO

## STEP 17: MODIFY THE PYTHON PROGRAM

Open the Python file:

```bash
nano test_project.py
```

Change the condition:

```python
if result == 30:
```

to:

```python
if result == 100:
```

Save and exit.

Now the calculation produces 30, but the program expects 100.

Therefore, the test should fail.

## STEP 18: COMMIT AND PUSH THE FAILURE TEST

```bash
git add test_project.py
```

```bash
git commit -m "Test CI pipeline failure scenario"
```

```bash
git push origin main
```

## STEP 19: VERIFY FAILURE IN GITHUB ACTIONS

1. Open GitHub.
2. Select the Actions tab.
3. Open the latest workflow run.
4. Select the test job.
5. Observe the Run Project Test step.

EXPECTED RESULT:

The Run Project Test step fails because the condition is incorrect.

The Generate Failure Report step runs.

The Run Prompt-Based Analysis step runs.

The Upload Execution Reports step runs.

The overall workflow will show failure because the test failed, even though the reporting steps succeeded.

---

# PART 11 – RESTORE THE SUCCESSFUL VERSION

## STEP 20: RESTORE THE PYTHON CONDITION

Open:

```bash
nano test_project.py
```

Change:

```python
if result == 100:
```

back to:

```python
if result == 30:
```

Save and exit.

## STEP 21: COMMIT AND PUSH THE RESTORED PROGRAM

```bash
git add test_project.py
```

```bash
git commit -m "Restore successful testing condition"
```

```bash
git push origin main
```

Open GitHub Actions and verify that the latest workflow completes successfully.

---

# PART 12 – DOWNLOAD THE GENERATED REPORTS

## STEP 22: DOWNLOAD WORKFLOW ARTIFACTS

1. Open the GitHub repository.
2. Click Actions.
3. Open the latest successful workflow run.
4. Scroll down to the Artifacts section.
5. Click project-execution-reports.
6. Download the ZIP file.

The ZIP file contains:

- report.txt
- actionable_report.txt

These files contain the execution result and prompt-based analysis.

---

# PART 13 – FINAL VERIFICATION

Verify the following:

1. New GitHub repository created.
2. Python testing program created.
3. GitHub Actions workflow configured.
4. Workflow executed successfully.
5. Success report generated.
6. Failure scenario tested.
7. Failure report generated.
8. Prompt-based analysis executed.
9. Reports uploaded as workflow artifacts.
10. Successful Python condition restored.
11. Final workflow execution completed successfully.

---

## VIVA QUESTIONS AND ANSWERS

**1. What is CI/CD?**

CI/CD stands for Continuous Integration and Continuous Delivery/Deployment. It automates software integration, testing and delivery.

**2. What is Continuous Integration?**

Continuous Integration is the process of frequently integrating code changes and automatically testing them.

**3. What is Continuous Delivery?**

Continuous Delivery ensures that tested software is kept ready for release.

**4. What is GitHub Actions?**

GitHub Actions is a GitHub automation platform used to build, test and automate software workflows.

**5. What is a workflow?**

A workflow is an automated sequence of jobs and steps defined in a YAML file.

**6. What is YAML?**

YAML is a human-readable data serialization format used for configuration.

**7. What is a runner?**

A runner is the machine or environment that executes GitHub Actions workflow jobs.

**8. What is an artifact?**

An artifact is a file or collection of files generated during a workflow and saved for later download.

**9. What is prompt engineering?**

Prompt engineering is the process of designing structured instructions to obtain useful outputs from an AI system or a prompt-based application.

**10. What is the purpose of the failure scenario?**

It verifies whether the pipeline can identify failed tests and generate an appropriate failure report.

**11. What is the purpose of actions/checkout?**

It checks out the repository so that workflow steps can access its files.

**12. What is the purpose of workflow_dispatch?**

It allows a user to start a workflow manually from GitHub.

**13. What is the purpose of success()?**

It checks whether previous steps in the job have succeeded.

**14. What is the purpose of failure()?**

It checks whether a previous step in the job has failed.

**15. What is the purpose of always()?**

It allows a step to run regardless of the result of previous steps, subject to cancellation and other workflow conditions.

---

## RESULT

Thus, a CI/CD pipeline was successfully implemented using GitHub Actions. A Python testing program was executed automatically whenever code changes were pushed to GitHub. Success and failure reports were generated, prompt-based analysis was performed, and execution reports were uploaded as downloadable workflow artifacts.
