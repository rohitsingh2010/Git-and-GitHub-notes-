# Git-and-GitHub-notes-
command and notes
## Git & GitHub: Fundamentals & Environment Setup

### Definitions
* **Version Control Software (VCS):** A system that tracks changes to files over time, allowing multiple developers to collaborate, integrate code, and monitor modifications.
* **Git:** A local version control software used to manage changes in project source code on a developer's machine.
* **GitHub:** A cloud-based platform that hosts central repositories, enabling team collaboration, code integration, and project tracking.
* **Repository (Repo):** A storage space (folder) where project source code and configuration files are kept.

### Environment Setup
1. **GitHub Account:** Register at *github.com* to create a central location for your projects.
2. **Git Client:** Download and install the Git client software to communicate with GitHub.
3. **Git Bash:** The Command Line Interface (CLI) used to execute Git commands.

### Initial Configuration
Before performing operations, identify yourself to the Git client. This is a one-time process:

## Bash command --
**git config --global user.name Rohit Singh
** git config --global user.email rohitsinghg20@gmail.com

## If its needed to change these setting 
**git config --global --unset user.name Rohit Singh

### Core Git Architecture
* **Working Tree:** Your local project folder where you actively create and modify files.
* **Staging Area:** An intermediate zone where you select which files are ready for commit.
* **Local Repository:** Where your committed changes are stored on your machine.
* **Central/Remote Repository:** The version of your project stored on GitHub for global team access.

### Basic Workflow Commands
* **git init:** Initializes a new local(working tree) Git repository (creates the `.git` folder).
* lenovo@DESKTOP-GJNC3T8 MINGW64 /Git practice (master)
$ git init
Initialized empty Git repository in C:/Other software/Git/Git practice/.git/

lenovo@DESKTOP-GJNC3T8 MINGW64 /Git practice (master)
$ git init
Reinitialized existing Git repository in C:/Other software/Git/Git practice/.git/


* **git status:** Displays the status of files (e.g., tracked, untracked, or modified).
* **git add <file>:** Moves specific files from the Working Tree to the Staging Area.
* **git commit -m "message":** Saves changes from the Staging Area to your Local Repository with a descriptive note.
* **git push:** Uploads local commits to the Central (Remote) Repository.

  <img width="947" height="410" alt="image" src="https://github.com/user-attachments/assets/fd8417c1-3afc-4f30-96d8-27714965ad36" />
 **Git workflows** and practical commands. Understanding these concepts, along with how to track file statuses via terminal colors, is fundamental to mastering the **Git lifecycle**.

### Key Git Architecture
 **Working Tree:** The local project folder where you create and modify files. Files here are "untracked" or "modified" and initially appear in **red** when you run `git status` 
 **Staging Area:** An intermediate zone for files prepared for a commit Once you add a file, it turns **green** in `git status`, signifying it is eligible for a commit.
 **Local Repository:** The version-controlled history stored on your machine. Running `git commit` moves staged (green) files here.
* **Central Repository:** A remote location (e.g., *GitHub*) where code is integrated for team access.

### Essential Git Commands
1. `git init`: Initializes a project folder as a Git repository.
2. `git add`: Moves files from the working tree to the staging area. 
3. `git commit`: Saves staged files to the local repository. Use `-m` to add a descriptive message.
4. `git push`: Transfers committed files from the local to the central repository.
5. `git status`: Checks the state of files (unstaged vs. staged).
6. `git log`: Views the history of your commits.
7. `git restore`: Use `git restore --staged <file>` to unstage a file without losing changes.
8. `git rm`: Removes a file from the project.
9. `git clone`: Downloads an entire repository from a central server.
10. `git pull`: Downloads and integrates latest changes from the central repository.
11. `git remote add`: Links your local repository to a specific central repository URL.


What is the difference between pull and clone?

* **Git Clone:** Use this command **only once** when you first join a project. It downloads the entire repository, including all files and history, from the central server to your local machine.
* **Git Pull:** Use this command **on a daily basis** (or whenever you start your work) to download only the latest updates or changes made by other developers to your existing local project. 

In short, **clone** is for grabbing the full project at the start, while **pull** is for keeping your local files in sync with the latest progress from the team.


### Workflow Summary & File Colors
* **Working Tree (Red state):** You create or update files. They are visible but sit outside the staging area.
* **Staging Area (Green state):** Run `git add` to prepare files for the next commit.
* **Local Repository:** Run `git commit` to permanently save your changes.
* **Central Repository:** Run `git push` to publish changes to the remote server.

### Additional Notes
* **README.md:** A user manual or description for your repository.
* **Git Ignore:** A file used to skip specific files or folders (like `target` or system configs) from Git operations.
* **Handling Conflicts:** When multiple developers modify the same code, you must manually resolve conflicts before committing and pushing.

Here is a comprehensive reference sheet of Git commands categorized by workflow stage.

---

## 1. Setup & Configuration

```bash
# Configure user details globally
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"

# View all active configuration settings
git config --list --show-origin

# Set default editor (e.g., VS Code)
git config --global core.editor "code --wait"

# Set default initial branch name to main
git config --global init.defaultBranch main

# Set useful command aliases
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.st status

```

---

## 2. Starting a Project

```bash
# Initialize a new Git repository in the current folder
git init

# Initialize with a specific default branch name
git init -b main

# Clone an existing remote repository
git clone <repo-url>

# Clone a specific branch directly
git clone -b <branch-name> <repo-url>

# Clone with limited history depth (shallow clone)
git clone --depth=1 <repo-url>

```

---

## 3. Working Directory & Staging Area

```bash
# Check working tree and staging area status
git status
git status -s                      # Short/compact status

# Stage changes
git add <file>                     # Stage a specific file
git add .                          # Stage all files in current directory
git add -A                         # Stage all changes across entire repository
git add -p                         # Interactive staging (hunk by hunk)

# Unstage files (keep file changes intact)
git restore --staged <file>        # Modern syntax
git reset HEAD <file>              # Legacy syntax

# Discard working tree changes (irreversible)
git restore <file>                 # Discard changes to a specific file
git restore .                      # Discard changes to all modified files
git checkout -- <file>             # Legacy syntax to discard changes

# File removal and renaming
git rm <file>                      # Remove file from disk and staging area
git rm --cached <file>             # Untrack file (keep local file on disk)
git mv <old-name> <new-name>       # Rename or move a tracked file

```

---

## 4. Comparing Changes (`diff`)

```bash
# Compare working tree vs. staging area (unstaged modifications)
git diff

# Compare staging area vs. last commit (what will be committed)
git diff --staged                  # or: git diff --cached

# Compare working tree vs. a specific commit/branch
git diff <branch-name>
git diff <commit-hash>

# Compare two branches or commits
git diff <branch-1>..<branch-2>

# Show file names only with changes
git diff --name-only

```

---

## 5. Committing Changes

```bash
# Standard commit
git commit -m "Your commit message"

# Stage and commit tracked files in one command
git commit -am "Your commit message"

# Multi-line commit message
git commit -m "Title" -m "Detailed description body"

# Amend the most recent commit (edit message or add forgotten staged files)
git commit --amend -m "Updated commit message"
git commit --amend --no-edit        # Add files without altering commit message

```

---

## 6. Inspecting History & Logs

```bash
# Standard commit log
git log

# Compact single-line view
git log --oneline

# Graphical commit history showing branches and merges
git log --oneline --graph --all --decorate

# Show recent commits with file change statistics
git log -n 5 --stat

# Search commit history by commit message text
git log --grep="bugfix"

# View changes introduced by a specific commit
git show <commit-hash>

# Line-by-line attribution of who edited a file and when
git blame <file>

```

---

## 7. Branching

```bash
# List branches
git branch                         # List local branches
git branch -r                      # List remote branches
git branch -a                      # List all (local + remote) branches

# Create branches
git branch <new-branch>            # Create branch without switching
git checkout -b <new-branch>       # Create and switch (classic)
git switch -c <new-branch>         # Create and switch (modern)

# Switch branches
git switch <branch-name>           # Modern syntax
git checkout <branch-name>         # Classic syntax

# Rename branches
git branch -m <old-name> <new-name>
git branch -m <new-name>           # Rename current branch

# Delete branches
git branch -d <branch-name>        # Safe delete (only if fully merged)
git branch -D <branch-name>        # Force delete unmerged branch
git push <remote> --delete <branch-name>  # Delete branch on remote

```

---

## 8. Merging & Rebasing

```bash
# Merge another branch into your current branch
git merge <branch-name>

# Force a merge commit (even if fast-forward is possible)
git merge --no-ff <branch-name>

# Abort a merge in progress during a conflict
git merge --abort

# Rebase current branch onto another branch
git rebase <base-branch>

# Interactive rebase (squash, edit, drop previous commits)
git rebase -i HEAD~<number-of-commits>

# Managing rebase conflicts
git rebase --continue
git rebase --skip
git rebase --abort

# Apply a specific commit from another branch to the current branch
git cherry-pick <commit-hash>
git cherry-pick --abort

```

---

## 9. Remotes & Collaboration

```bash
# Manage remotes
git remote -v                      # List connected remotes with URLs
git remote add <name> <url>        # Add a new remote (usually named origin)
git remote rename <old> <new>      # Rename remote
git remote remove <name>           # Remove remote link
git remote show <name>             # Inspect remote branches and setup

# Syncing data
git fetch <remote>                 # Download remote changes without merging
git fetch --prune                  # Fetch and delete stale remote tracking branches

# Pulling (Fetch + Merge/Rebase)
git pull <remote> <branch>
git pull --rebase <remote> <branch> # Pull using rebase instead of merge

# Pushing
git push <remote> <branch>
git push -u <remote> <branch>      # Push and set upstream tracking
git push --all                     # Push all local branches
git push --tags                    # Push tags to remote
git push --force-with-lease        # Safe force push (rejects if remote updated)

```

---

## 10. Temporary Storage (`git stash`)

```bash
# Save modified and staged working directory changes
git stash
git stash push -m "work-in-progress description"

# Include untracked files in stash
git stash -u                       # or: git stash --include-untracked

# Inspect stashes
git stash list                     # List saved stashes
git stash show -p stash@{0}        # View diff of a stash

# Restore stashes
git stash apply                    # Apply most recent stash and keep it in stash list
git stash pop                      # Apply most recent stash and remove it from list
git stash apply stash@{1}          # Apply a specific stash

# Clean up stashes
git stash drop stash@{0}           # Delete a specific stash
git stash clear                    # Delete all stashes

```

---

## 11. Undo, Reset & Revert

```bash
# Soft reset: moves HEAD back, keeps changes in Staging Area
git reset --soft HEAD~1

# Mixed reset (default): moves HEAD back, keeps changes in Working Tree (unstaged)
git reset --mixed HEAD~1

# Hard reset: moves HEAD back, discards all working directory changes (destructive)
git reset --hard HEAD~1
git reset --hard <commit-hash>

# Safely revert a past commit by creating an inverted new commit
git revert <commit-hash>
git revert -n <commit-hash>        # Revert without automatically committing

# Safety net: view log of all HEAD movements (used to recover lost commits)
git reflog

```

---

## 12. Tagging

```bash
# List tags
git tag

# Lightweight tag (points directly to commit)
git tag v1.0.0

# Annotated tag (recommended for releases: includes author, date, and message)
git tag -a v1.0.0 -m "Release version 1.0.0"

# Tag a past commit
git tag -a v0.9.0 <commit-hash> -m "Beta release"

# Push tags to remote
git push origin <tag-name>
git push origin --tags

# Delete tags
git tag -d <tag-name>              # Local delete
git push origin --delete <tag-name># Remote delete

```

---

## 13. Maintenance & Cleanup

```bash
# Remove untracked files from working tree
git clean -n                       # Dry-run: show what would be removed
git clean -f                       # Force removal of untracked files
git clean -fd                      # Force removal of untracked files and directories

# Run repository garbage collection and file optimization
git gc --prune=now

# Verify database integrity and find broken links
git fsck

```
