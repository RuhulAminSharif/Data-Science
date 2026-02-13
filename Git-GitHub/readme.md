## Setup

Set the name and email that will be attached to your commits and tags:

```bash
git config --global user.name "Your Name"
git config --global user.email "youremail@example.com"
```

## Starting a Project with Git

### Create a Local Repository

(Omit `<directory>` to initialize the current directory)

```bash
git init <directory>
```

Or:

```bash
git init
```

### Clone a Remote Repository

Example:

```bash
git clone https://github.com/username/repo.git
```


## Make a Change

### Add a File to Staging

Example (if `app.py` exists in your project folder):

```bash
git add app.py
```

### Stage All Files

`.` adds all files in the project folder to staging:

```bash
git add .
```

### Commit Staged Files

```bash
git commit -m "your message"
```

### Add All Tracked Changes & Commit

```bash
git commit -am "your message"
```


## Basic Git Concepts

* **main** → default development branch
* **origin** → default upstream repository
* **HEAD** → current branch
* **HEAD^** → parent of HEAD
* **HEAD~4** → great-great grandparent of HEAD


## Branches

### List Branches

```bash
git branch
```

* Add `-r` → show remote branches
* Add `-a` → show all branches

### Create a New Branch

```bash
git branch branch-name
```

### Switch to a Branch

```bash
git checkout branch-name
```

### Create & Switch to a New Branch

```bash
git checkout -b branch-name
```

### Delete a Merged Branch

```bash
git branch -d branch-name
```

### Force Delete a Branch

```bash
git branch -D branch-name
```

### Add a Tag to Current Commit

```bash
git tag v1.0
```


## Merging

### Merge Branch A into Branch B

```bash
git checkout branch-b
git merge branch-a
```

### Merge & Squash Commits

```bash
git merge --squash branch-name
```


## Ignoring Patterns

Prevent unintentional staging or committing of files.

Create a file named `.gitignore` with patterns using direct matches or wildcards.

### Example `.gitignore`

```
logs/
*.db
.idea
```

### Explanation

* `logs/` → ignores all files inside `logs` folder
* `*.db` → ignores all files with `.db` extension
* `.idea` → ignores IDE folder


## Undoing Things

### Move or Rename a File (and Stage)

```bash
git mv oldname newname
```

### Remove File from Working Directory & Staging

```bash
git rm filename
```

### Remove from Staging Only

```bash
git rm --cached filename
```


## Review Your Repository

### List New or Modified Files

```bash
git status
```

### View Commit History

```bash
git log
```

### Show Changes to Unstaged Files

```bash
git diff
```

For staged files:

```bash
git diff --cached
```

### Show Changes Between Two Commits

```bash
git diff commit1 commit2
```

### Show Full Commit Logs (with Renames)

```bash
git log --stat
```

### Show Commits that Changed a File (Across Renames)

```bash
git log --follow filename
```


## Synchronizing / Updating

### Add a Remote Repository

```bash
git remote add origin <repo-url>
```

### View Remote Connections

```bash
git remote -v
```

### Remove a Remote Connection

```bash
git remote remove origin
```

### Rename a Remote

```bash
git remote rename old-name new-name
```

### Fetch All Branches (No Merge)

```bash
git fetch
```

### Fetch a Specific Branch

```bash
git fetch origin branch-name
```

### Fetch & Merge Current Branch

```bash
git pull
```

### Rebase Local Changes (Clean Linear History)

```bash
git pull --rebase
```

### Push Local Content to Remote

```bash
git push
```

### Push to a Specific Branch

```bash
git push origin branch-name
```


# Example: Pushing a New Project to GitHub

## Project Structure

```
Project/
│
├── static/
├── .idea/
├── logs/
├── app.py
├── data.db
├── requirements.txt
└── .gitignore
```

## `.gitignore` Contents

```
logs/
*.db
.idea
```


## Create a Repository on GitHub

1. Go to GitHub
2. Log into your account
3. Click the **New Repository** button (top-right)
4. Do NOT initialize with README
5. Click **Create Repository**
6. You will receive a `.git` repository URL

Example:

```
https://github.com/user-name/example.git
```


## Order of Commands

```bash
git init
git add .
git commit -m "initial commit"
git branch -M main
git remote add origin https://github.com/user-name/example.git
git push -u origin main
```

All project files will be pushed except those listed in `.gitignore`.