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
