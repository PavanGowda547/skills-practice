# 1. Git Fundamentals

### Git
Git is a free, open-source version control system used to track changes in your code. It helps developers save different versions of their projects, go back to previous versions, and collaborate without losing their work.

### Version control
Version Control is a system that tracks changes made to files over time. It allows you to see what changed, who changed it, when it changed, and restore an older version if needed.

### Github
GitHub is an online platform that hosts Git repositories. It allows developers to store code online, collaborate with others, review code, and manage projects.

### Difference between Git and Github
- Git: A tool installed on your computer to track code changes.
- GitHub: An online platform where you can store and share Git repositories.

Think of Git as a tool and GitHub as a service that uses that tool.

### Distributed Version Control System
Git is a Distributed Version Control System, meaning every developer gets a complete copy of the project's history on their computer. You can work, commit changes, and view previous versions even without an internet connection.

### Repository (Repo)
A repository is a place where Git stores and manages your project files and their version history. It contains your project code along with information about its changes.

### Working Directory
The Working Directory is the folder where you create, edit, delete, or modify project files. These changes are not automatically saved as Git commits.

### Staging Area
The Staging Area is an intermediate area where you select which changes should be included in your next commit. You use the git add command to move changes from the Working Directory to the Staging Area.

###  Local Repository
A Local Repository is the Git repository stored on your own computer. It contains your project's committed history and allows you to manage changes without an internet connection.

### Remote Repository
A Remote Repository is a version of your repository hosted on another computer or server, usually on platforms like GitHub or GitLab. You can share your changes with others using commands like git push and git pull.

### Commit
A Commit is a snapshot of your project at a particular point in time. It saves the staged changes in your local repository along with a unique ID, author information, timestamp, and commit message.

Example:
```
git commit -m "Added login functionality"
```
### HEAD
HEAD is a pointer that tells Git which commit or branch you are currently working on. Usually, HEAD points to the latest commit of your currently checked-out branch.

### .git Folder
The .git folder is the hidden directory created when you initialize a Git repository using git init. It stores Git's internal information, including commit history, branches, configuration, and other repository metadata.

**Important**: If you delete the .git folder, your project files remain, but Git's version history and repository information are lost.

### Git Installation
Git Installation means installing the Git software on your computer so you can use Git commands.  

Step 1: Open the Git website
```
    Open your web browser.
    Visit https://git-scm.com/
    Click on Download.
```
Step 2: Choose your operating system
```
    Select your operating system (Windows, Mac, or Linux).
    Download the Git installer.
```
Step 3: Install Git
```
    Open the downloaded installer.
    Click Next.
    Keep the default settings.
    Click Next until you see the Install button.
    Click Install.
    Wait for the installation to finish.
    Click Finish.
```
Step 4 :   To verify Git Installation
```
git --version
```
If Git is installed correctly, it displays the installed Git version.

### Git Configuration
Git Configuration means setting up your identity and preferences so Git knows who is making commits.

For example:
```
git config --global user.name "Your Name"

git config --global user.email "you@example.com"
```
To check your configuration:
```
git config --list
```
The --global option applies these settings to all Git repositories for your user account.


### Understand the Git Workflow
```
Working Directory
       |
       | git add
       v
  Staging Area
       |
       | git commit
       v
 Local Repository
       |
       | git push
       v
 Remote Repository (GitHub)
```

### Practical Exercises
- [ ] Install Git.
- [ ] Configure Git username and email.
- [ ] Initialize a Git repository.
- [ ] Create files and folders.
- [ ] Understand the working directory.
- [ ] Understand the staging area.
- [ ] Understand local and remote repositories.
- [ ] Understand how commits work.