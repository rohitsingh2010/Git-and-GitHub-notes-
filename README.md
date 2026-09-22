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

 **concurrent development and merge conflicts**:

### Concurrent Development & Conflicts
* **Collaborative Workflow:** A common professional scenario where multiple developers (e.g., *John* and his colleague) work simultaneously on the same project and, specifically, the same *Java* (file) class file and same line in the **central repository** so confilict will occur.
* **The Nature of Conflicts:** When two developers modify the same file and same lines of code at a same time, *Git* cannot automatically decide which version is correct. This results in a **merge conflict** will occurs.
* **Managing Reality:** expected part of the software development lifecycle when working in a team. It is not necessarily an error, but a signal that human intervention is needed.

### The Resolution Process
If a conflict occurs, follow these steps to resolve it:
1. **Acknowledge the Conflict:** Typically identified when a `git pull` operation fails due to discrepancies between the local and central versions. in code- (`<<<<<<<`, `=======`, `>>>>>>>`). Leaving these in the file will cause syntax errors or compiler breaks
2. **Manual Intervention:** Developers must open the conflicted file, compare the changes, and manually choose or merge the correct code logic.
3. **Finalize Integration:** Once the manual edits are made, you must save, **commit** the resolution, and then **push** the changes to the central repository to complete the sync.
**To better understand the resolution process described between** here are the specific **Git commands** you must use to handle conflicts in a collaborative environment:

### Conflict Resolution Workflow

When multiple developers modify the same file and same lines, your `git push` will be rejected. Follow these steps to resolve it:

1.  **Identify the Conflict:** Run `git pull` to fetch and attempt to merge the latest changes from the central repository. When the conflict occurs, Git will halt the operation and mark the affected files.
2.  **Manually Edit:** Open the conflicted files. Look for the "junk characters" (markers Git inserts) and decide which code to keep.
3.  **Check Status:** Use `git status` to verify which files are currently in a conflicted state.
4.  **Add Resolved Files:** Once you have manually fixed the code, run `git add <filename>` (or `git add .`) to move the resolved file from the working tree to the staging area.
5.  **Commit the Fix:** Run `git commit -m "conflict resolved"` to save the resolution to your local repository.
6.  **Push the Changes:** Finally, run `git push` to send your clean, merged code to the central repository.

### Key Command Summary
* **`git pull`**: Downloads the latest changes from the remote server. If you lack the latest code before pushing, this is the command that triggers the conflict detection .
   **`git status`** | Lists all unmerged paths and identifies exactly which files require manual review. 
**`git diff`** Shows line-by-line differences between local changes and incoming changes before editing. 
* **`git add`**: Required to tell Git that you have finished manually resolving the conflict and the file is ready for the next step. **git add <filename>  Or stage all resolved files: git add**.
* **`git commit`**: Finalizes the resolution locally with a clear message explaining that the conflict was resolved.
* **`git push`**: Pushes your successfully integrated code to the central repository so other team members can see your work.
  
### when conflict will not occur -
If we are modifying  different files then conflict will not occurred 
### how to identify working directory
.git folder will be available 

if it is not showing go to file explorer options and in view option you need to click on the show hidden files.

### what is Git GUI-
it is a desktop tool to perform git operations.
execute the below command in working tree to open the git gui
** $git gui  
<img width="1107" height="543" alt="image" src="https://github.com/user-attachments/assets/b2a26ef7-4b10-4b73-bd36-22a9da195a8d" />

<img width="1130" height="582" alt="image" src="https://github.com/user-attachments/assets/3911b475-4705-4a50-833a-09f286bc7ec7" />
<img width="1132" height="606" alt="image" src="https://github.com/user-attachments/assets/ffa8eeef-16bf-4bf7-a0a2-f40c6c576e8c" />

### what is .gitignore file
it is used to specify files and folders to skip from git operations. 
git hub is to update the source code not for bit codes

### How to work with branches
**Git Branches**
<img width="798" height="375" alt="image" src="https://github.com/user-attachments/assets/cabc3bea-bd27-4c8b-ba83-5b354242a5ac" />
## When multiple team is working on the same repo then project delivery will become very difficult.
** To make our project delivery process simple. we need to maintain multiple branchess in git hub repo.
## Note For every team one git branch is recommended.
** by using branches, multiple team can work parallelly.
<img width="692" height="309" alt="image" src="https://github.com/user-attachments/assets/45c4d6b6-50ad-49a6-a3bd-b98700e952b1" />
## Branch merging-
<img width="759" height="358" alt="image" src="https://github.com/user-attachments/assets/8562f420-0f3a-4bbb-9ad0-7020cd2bae19" />

**By using pull request we can merge brach into main branch
## Lab Task
** Go to git hub repository and create develop branch from main branch
** clone git repo( by default main branch will come)
   $ git clone <url>
** switch from main to develop
   $git checkout develop
** Create a file and push to develop branch
** Create pull request and merge develop branch changes to main branch. 
End of the day code will be available in main branch.

## Managing Workflow Interruptions
**Git Stash**: A key concept introduced is git stash . 
When a developer is in the middle of a task but is suddenly assigned a higher-priority, critical fix, they can use git stash to move their current, uncommitted changes to a temporary storage area. This leaves the working tree clean and ready for the urgent task.
Restoring Progress: Once the high-priority task is completed, the developer can use **git stash apply** to bring their original, in-progress code back into the working tree to continue their work.
## Advanced Repository Operations
Local History Management: ** git reset**  how to remove local commits using either soft or hard resets. This is useful for undoing work that was committed locally but should not be pushed to the central repository.
Forking and Collaboration: the concept of forking , which allows developers to copy another user's repository to their own account to suggest changes. It also covers adding collaborators  to grant specific permissions for pushing code to a shared repository.

## Utility Commands for Workflow
 * git stash : Use this to temporarily save uncommitted changes in your working tree to a backup area. This is essential when you are interrupted and need to switch to a high-priority task without losing your current progress.
* git stash apply : Once your urgent task is finished, this command restores your stashed changes back into your working tree so you can resume your original work.
* git reset : A powerful command to remove local commits. You can use soft reset to keep changes in the staging area or hard reset to delete changes entirely from the working tree.
* Reset vs. Revert: A key distinction: git reset is used for removing local commits, while git revert is used for undoing commits already pushed to the central repository ** git revert <commint ID>
* git cherry-pick: Instead of merging an entire branch, this command allows you to integrate a specific, single commit from one branch into another.
## Remote Operations
* git fetch : This downloads changes from the remote to your local repository without merging them immediately into your working tree. Use this for more control compared to git pull.
* git fork : This allows you to create a personal copy of someone else's repository on your own GitHub account, making you the owner of that copy so you can propose or implement changes.


