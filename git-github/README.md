# Git & GitHub for DevOps 🌿

This section contains my Git and GitHub learning notes, hands-on practice, and lab exercises completed as part of my DevOps learning journey.

---

# Why Git?

Before Version Control Systems, developers often managed files like:

```text
project_v1
project_final
project_final_latest
project_final_latest2
```

This created confusion and made collaboration difficult.

Git solves this problem by tracking changes, maintaining history, and enabling collaboration.

---

# What is Git?

Git is a Distributed Version Control System (DVCS) used to:

* Track file changes
* Maintain version history
* Collaborate with teams
* Restore previous versions
* Manage software projects

### Key Learning

Git does not just store files.

Git stores the history of changes.

---

# Git Architecture

Git works using three important areas:

## 1. Working Area

Where files are created and modified.

Example:

```bash
echo "Hello Git" > file.txt
```

---

## 2. Staging Area

Temporary area used to prepare changes before saving.

Example:

```bash
git add file.txt
```

---

## 3. Repository

Permanent storage of project history.

Example:

```bash
git commit -m "Added file"
```

---

# Git Workflow

```text
Working Area
      ↓
Staging Area
      ↓
Repository
```

---

# Git Configuration

Configure user information:

```bash
git config --global user.name "Your Name"

git config --global user.email "your@email.com"
```

Verify configuration:

```bash
git config --list
```

---

# Core Commands Practiced

## Check Repository Status

```bash
git status
```

Purpose:

* View modified files
* View staged files
* View untracked files

---

## Add Files

Add specific file:

```bash
git add file.txt
```

Add all files:

```bash
git add .
```

Purpose:

Move changes from Working Area to Staging Area.

---

## Commit Changes

```bash
git commit -m "Added new feature"
```

Purpose:

Create a permanent save point.

---

# .gitignore

Used to ignore unnecessary files.

Example:

```text
*.log
temp/
node_modules/
```

Purpose:

Prevent unwanted files from being tracked.

---

# Remote Repositories

GitHub is used to store repositories remotely.

## Connect Local Repository

```bash
git remote add origin https://github.com/username/repository.git
```

Verify:

```bash
git remote -v
```

---

## Push Changes

First push:

```bash
git push -u origin main
```

Future pushes:

```bash
git push
```

---

## Pull Changes

```bash
git pull origin main
```

Purpose:

Download and merge latest changes.

---

## Clone Repository

```bash
git clone https://github.com/username/repository.git
```

Purpose:

Create a local copy of a remote repository.

---

# Branching

Branches allow developers to work independently without affecting the main code.

## View Branches

```bash
git branch
```

---

## Create Branch

```bash
git branch feature-login
```

---

## Create and Switch

```bash
git checkout -b feature-login
```

---

## Switch Branch

```bash
git checkout feature-login
```

---

## Delete Branch

```bash
git branch -d feature-login
```

---

# Merge

Merge combines changes from one branch into another.

Example:

```bash
git checkout main

git merge feature-login
```

Purpose:

Integrate completed work into the main branch.

---

# Merge Conflict Practice

A merge conflict occurs when two branches modify the same content differently.

Example:

```bash
git merge feature-conflict
```

Resolution Steps:

1. Open conflicting file
2. Edit manually
3. Save changes
4. Stage changes

```bash
git add .
```

5. Complete merge

```bash
git commit -m "resolved conflict"
```

---

# Revert

Used to safely undo changes.

View history:

```bash
git log --oneline
```

Revert commit:

```bash
git revert HEAD
```

Purpose:

Create a new commit that reverses previous changes.

---

# Stash

Used to temporarily save unfinished work.

Save changes:

```bash
git stash
```

View stash:

```bash
git stash list
```

Restore changes:

```bash
git stash pop
```

Apply without deleting:

```bash
git stash apply
```

Purpose:

Switch tasks without losing work.

---

# Hands-on Practice Completed

## Git Basics

* Repository initialization
* Tracking files
* Staging files
* Creating commits

## GitHub Integration

* Connecting remote repositories
* Pushing code
* Pulling updates
* Cloning repositories

## Branching

* Creating branches
* Switching branches
* Merging branches

## Advanced Operations

* Merge conflicts
* Revert
* Stash

---

# Key Skills Gained

✅ Version Control Concepts

✅ Repository Management

✅ Branching & Merging

✅ GitHub Integration

✅ Conflict Resolution

✅ Revert Operations

✅ Stash Operations

✅ Collaborative Development Workflow

---

# DevOps Relevance

Git is one of the most important tools in DevOps.

These skills are used daily for:

* Infrastructure as Code
* CI/CD Pipelines
* Source Code Management
* Team Collaboration
* Release Management

Understanding Git is essential before moving into advanced DevOps tools such as Docker, Kubernetes, and CI/CD platforms.
