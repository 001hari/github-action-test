this is a testing of fetch and pull 

input: testing for pull req to trigger the workflow 

# Section 1: Core Mental Model (Must-pass)

# Q1.
# A workflow file exists, but nothing runs when you push code.
# Give three independent reasons why this can happen.

# Q2.
# Explain the exact difference between:

# jobs

# steps

# actions

# (one line each)

# Section 2: Events & Triggers (Critical)

# Q3.
# What is the difference between:

# workflow_dispatch

# repository_dispatch

# When would you choose one over the other?

# Q4.
# A workflow should:

# Run on push

# Only on main

# Only when files inside /backend change

# Write only the on: section (no full workflow).

# Section 3: Runners & Execution (Very Important)

# Q5.
# True or False (justify in one line):

# Files created in Job A are automatically available in Job B.

# Q6.
# Why is actions/checkout almost always the first step in a job?

# What exactly breaks if you remove it?

# Section 4: Environment, Secrets & Security

# Q7.
# Where is this accessible and why?

# env:
#   NODE_ENV: production


# Is it available:

# Only in one step?

# Only in one job?

# Entire workflow?

# Explain.

# Q8.
# Why is GITHUB_TOKEN safer than using a personal access token?

# Give two reasons.

# Section 5: Expressions & Conditions (Senior Signal)

# Q9.
# What does this do?

# if: failure()


# Where is it most commonly used and why?

# Q10.
# Explain what matrix actually expands into during runtime.

# What problem does it solve?

# Section 6: Docker & Services (Real-World)

# Q11.
# Difference between:

# Job-level container

# Service container

# Give one real use case for each.

# Section 7: Control & Reliability

# Q12.
# When would you use:

# continue-on-error

# timeout-minutes

# Give one realistic scenario for each.

# Evaluation Rule (Transparent)

# You are ready for the next module if:

# You confidently answer 8+ questions

# You clearly understand why, not just what

# Reply with:

# A1: ...
# A2: ...
# ...


# After your answers:

# I will correct only where needed

# I will not repeat basics

# Then we move directly to automated testing + deployment pipelines


A1. three reasons are a. no trigger on push b. no jobs written c, forgot to write the runs-on

A2. jobs can have multiple steps to run while step have sequence of steps wriiten to run in the vm and action is the exact code that we have to run, jobs contain steps and steps contain action

A3. skip

A4. on: 
    push:
      branch: main /backend
    
A5. false we have to write needs

A6. it fetched the repo code to be executable in vm

A7. entire workflow beacuse we write this in top

A8. it is stored in secrest of github repo so no one can see the actual value

A9.it return true if prev step has error and false if no error 

A10. skip skip skip


# Mandatory Fix Round (Short)

# Answer only these 4. No skipping.

# Q1

# Difference between:

# workflow_dispatch

# repository_dispatch

# Q2

# Why needs does NOT share files between jobs?

# Q3

# What does a matrix with:

# node: [16, 18]
# os: [ubuntu-latest, windows-latest]


# expand into?

# Q4

# One reason not to use a personal access token in CI.

A1. workflow dispatch is used to trigger manual changes like ui/api
while repository_dispatch is used to trigger event throgh external event 

A2. needs only tell the runner to exe the needes before this step it is used to make steps run in serial

A3. it will run both ubuntu-latest and windows-latest node version 16 and 18

A4. skip

# Q1. Triggers & Filters (Critical)

# You want a workflow that:

# Runs on push

# Only on branch main

# Only when files in backend/ or shared/ change

# Should NOT run when only README.md changes

# Write only the on: block.

# Q2. workflow_dispatch vs repository_dispatch

# You have:

# A frontend repo

# A backend repo

# After backend deploys successfully, it should trigger a workflow in frontend automatically.

# Which event do you use and why?
# (Name the event + one-line reason.)

# Q3. Job Isolation (Very Important)

# True or False (justify):

# If Job A installs dependencies and Job B uses needs: A, Job B can use those installed dependencies.

# Q4. Matrix Expansion (Must be clear)

# Given:

# matrix:
#   node: [18, 20]
#   os: [ubuntu-latest, windows-latest]


# Answer:

# How many job runs will happen?

# Name one real reason to use this matrix in CI.

# Q5. GITHUB_TOKEN vs PAT (Security)

# Give two reasons why GITHUB_TOKEN is safer than a Personal Access Token.

# Q6. Conditional Execution

# When would you use:

# if: failure()


# Give one real CI/CD use case.

# How to Reply
# A1:
# A2:
# A3:
# A4:
# A5:
# A6:
    
  A1.on:
      push:
        branchs: main
        path: backend/**
  A2. i will use repository_dispatch beacuse it help us to write trigger that happen on external event

  A3. No needs only tell us how to run the jobs sharing of dependencies or other things can be done by using artifacts or exernal storage

  A4. 4
      when we want to run the jobs in multiple env with different different os and versions

  A5. github token is auto rotated and short lived 

  A6. when i want to know that a prev job or step is canceled or error i will use this function

testing...................
testing.2.................
