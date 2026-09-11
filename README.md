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
git config --global user.name Rohit Singh
git config --global user.email rohitsinghg20@gmail.com

## If its needed to change these setting 
git config --global --unset user.name Rohit Singh

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



