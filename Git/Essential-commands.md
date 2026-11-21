# 2. Essential Git Commands

| Command | Purpose | Simple Explanation | Example |
|---|---|---|---|
| `git init` | Initialize a repository | Creates a new Git repository in your project folder so Git can start tracking changes. | `git init` |
| `git clone` | Download a repository | Copies an existing remote repository to your computer, including its files and commit history. | `git clone https://github.com/user/project.git` |
| `git status` | Check file status | Shows which files are new, modified, deleted, staged, or not yet tracked by Git. | `git status` |
| `git add` | Stage changes | Adds new or modified files to the staging area so they can be included in the next commit. | `git add index.html` |
| `git commit` | Save changes | Saves the staged changes as a new version in the Git repository with a descriptive message. | `git commit -m "Initial commit"` |
| `git log` | View commit history | Displays previous commits, including their IDs, authors, dates, and messages. | `git log --oneline` |
| `git diff` | Compare changes | Shows the differences between your modified files and the previous version, helping you review changes before committing. | `git diff` |
| `git show` | Inspect a commit | Displays details of a commit, including its message and the changes made in that commit. | `git show` |
| `git restore` | Restore file changes | Discards unstaged changes in a file or removes a file from staging without deleting its contents. | `git restore index.html` |
| `git reset` | Reset HEAD or staging changes | Moves the current branch to an earlier commit or removes files from staging. Depending on the option, it can also discard changes. | `git reset HEAD index.html` |
| `git revert` | Undo changes through a new commit | Reverses the changes made by a previous commit without deleting the original commit from history. | `git revert <commit-id>` |
| `git rm` | Remove tracked files | Deletes a tracked file from your project and stages its removal for the next commit. | `git rm old-file.txt` |
| `git mv` | Rename or move tracked files | Renames a file or moves it to another folder and stages the change. | `git mv old.txt new.txt` |
| `git stash` | Temporarily save changes | Temporarily stores your uncommitted changes so you can work on something else without committing them. | `git stash` |
| `git clean` | Remove untracked files | Removes files that Git is not tracking from your project directory. | `git clean -n` |
| `git reflog` | View reference history | Shows the history of changes to HEAD and branch references, helping you find commits after operations like reset. | `git reflog` |
| `git config` | Configure Git | Sets Git preferences such as your username, email address, and default settings. | `git config --global user.name "John"` |
| `git help` | Access Git documentation | Displays documentation and usage instructions for Git commands. | `git help commit` |
---

<br><br>
Let's explore each command with simple and easy steps :

## 1. `git init`
Initialize a new Git repository. This command tells Git to start tracking your project.  

Step-by-step practical implementation :

Step 1. Create a project folder

Create a folder on your computer called:
```
my-first-project
```
Step 2. Open the folder in VS Code
- Open VS Code.
- Click File → Open Folder.
- Select my-first-project.

Step 3. Open the terminal

In VS Code:
- Click Terminal.
- Select New Terminal.

Step 4. Execute the command

```
git init
```
Press Enter.

Step 5. Check the output

You should see something similar to:
```
Initialized empty Git repository in .../my-first-project/.git/
```
Success Your project is now initialized as a Git repository.

Step 6. Verify it

Execute:
```
git status
```
You should see something similar to:
```
On branch master

No commits yet

nothing to commit
```
What happened behind the scenes?
- Git created a hidden folder called .git.
- This folder stores your repository's history and configuration.
- Your project is now ready for Git version control

## 2. `git clone`

Download an existing Git repository to your computer.
It copies someone else's project from GitHub (or another Git server) to your computer, including its commit history.

### Step-by-step practical implementation

Step 1. Open GitHub

- Go to [GitHub](<https://github.com?utm_source=chatgpt.com>).
- Find a repository you want to download.
- Open that repository.

Step 2. Copy the repository URL

- Click the green Code button.
- Select HTTPS.
- Copy the URL.

Example:

```bash
https://github.com/octocat/Hello-World.git
```

Step 3. Open your VS Code terminal

Navigate to the folder where you want to download the project.

Step 4. Execute the command

```bash
git clone https://github.com/octocat/Hello-World.git
```

Step 5. Check the result

Git will download the project into a new folder called `Hello-World`.

Step 6. Open the downloaded project

```bash
cd Hello-World
```

Step 7. Verify the repository

```bash
git status
```

You should see something similar to:

```bash
On branch master
Your branch is up to date with 'origin/master'.

nothing to commit, working tree clean
```

### What happened behind the scenes?

- Git downloaded the project files.
- Git downloaded the commit history.
- Git created a local repository.
- Git connected your local repository to the remote repository.

Important difference:

- `git init` → Creates a new local Git repository.
- `git clone` → Downloads an existing Git repository.

## 3. `git status`

Check the status of your project files.
It tells you which files are new, modified, deleted, staged, or committed.

### Step-by-step practical implementation

Step 1. Open your Git project

Open the project folder in VS Code.

Step 2. Create a new file

Create a file called:

```text
index.html
```

Step 3. Add some content

Inside `index.html`, write:

```html
<h1>Hello Git!</h1>
```

Save the file.

Step 4. Open the terminal

Execute:

```bash
git status
```

Step 5. Check the output

You should see something similar to:

```bash
Untracked files:
  index.html
```

What this means, Git has detected your new file, but it is not tracking it yet.

Step 6. Modify the file

Change the content to:

```html
<h1>Hello Git! I am learning Git.</h1>
```

Save the file.

Run:

```bash
git status
```

Git will show you the file's current status.

### Remember

- Untracked = New file Git hasn't started tracking.
- Modified = Existing tracked file has been changed.
- Staged = File is prepared for the next commit.

## 4. `git add`

Stage changes. It tells Git which files you want to include in your next commit.

### Step-by-step practical implementation

Step 1. Open your project

Open your existing Git project in VS Code.

Step 2. Check the current status

Run:

```bash
git status
```

You should see `index.html` listed as an untracked or modified file.

Step 3. Add the file to staging

Run:

```bash
git add index.html
```

This adds only `index.html` to the staging area.

Step 4. Verify the result

Run:

```bash
git status
```

You should see:

```bash
Changes to be committed:
  new file: index.html
```

If the file was previously tracked, you may see:

```bash
Changes to be committed:
  modified: index.html
```

Successfully staged Other useful variations

| Command | Purpose |
| --- | --- |
| `git add index.html` | Add one file |
| `git add .` | Add all changes in the current directory and its subdirectories |
| `git add *.html` | Add matching HTML files |

### Remember

- `git status` = Check your changes.
- `git add` = Prepare your changes.
- `git add` does not permanently save a commit.

## 5. `git commit`

Save changes.
It saves your staged changes as a new version in your Git repository.

### Step-by-step practical implementation

Step 1. Check staged files

Run:

```bash
git status
```

Make sure `index.html` appears under Changes to be committed.

Step 2. Execute the commit command

Run:

```bash
git commit -m "Initial commit"
```

Step 3. Understand the command

- `git commit` → Saves staged changes.
- `-m` → Allows you to write a commit message.
- `"Initial commit"` → Describes what you saved.

Step 4. Check the output

You should see something similar to:

```bash
[master abc1234] Initial commit
 1 file changed, 1 insertion(+)
 create mode 100644 index.html
```

Step 5. Verify the result

Run:

```bash
git status
```

Expected output:

```bash
nothing to commit, working tree clean
```

Commit successful, Remember the Git workflow

```bash
git status
git add index.html
git commit -m "Initial commit"
```

- `git add` prepares changes.
- `git commit` saves changes in Git history.

## 6. `git log`

View commit history.
It shows all the commits you have made in your Git repository.

### Step-by-step practical implementation

Step 1. Open your project terminal

Make sure you are inside your Git project folder.

Step 2. Execute the command

```bash
git log
```

Step 3. Check the output

You should see something similar to:

```bash
commit a1b2c3d4e5f6
Author: John <john@example.com>
Date:   Sat Nov 21 14:00:00 2026

    Initial commit
```

Step 4. Understand the output

- `commit` → Unique ID of the commit.
- `Author` → Person who created the commit.
- `Date` → When the commit was created.
- `Initial commit` → Commit message.

Step 5. Try a shorter version

Execute:

```bash
git log --oneline
```

Expected output:

```bash
a1b2c3d Initial commit
```

This displays commits in a short, single-line format.

Step 6. Create another commit to practise

- Open `index.html`.
- Change the heading to:

```html
<h1>Learning Git Commands</h1>
```

- Save the file.
- Run:

```bash
git add index.html
git commit -m "Update heading"
```

- Now execute:

```bash
git log --oneline
```

You should see two commits\!

### Remember

- `git log` → Displays detailed commit history.
- `git log --oneline` → Displays short commit history.

## 7. `git diff`

Compare changes.
Shows exactly what you changed in your files compared to the last committed version.

### Step-by-step practical implementation

Step 1. Open your project

Open `index.html` in VS Code.

Step 2. Modify the file

Change the heading from:

```html
<h1>Learning Git Commands</h1>
```

To:

```html
<h1>Learning Git with ChatGPT</h1>
```

Save the file.

Step 3. Execute the command

Open your terminal and run:

```bash
git diff
```

Step 4. Understand the output

You should see something similar to:

```diff
-<h1>Learning Git Commands</h1>
+<h1>Learning Git with ChatGPT</h1>
```

What does this mean?

- `-` means the old line was removed.
- `+` means the new line was added.
- Git shows the differences between your modified file and the last commit.

Step 5. Try another command

Run:

```bash
git diff --staged
```

This shows differences between staged changes and the last commit.

Step 6. Practise staging your changes

Run:

```bash
git add index.html
```

Now execute:

```bash
git diff
```

You should see no output because the changes are staged.

Now execute:

```bash
git diff --staged
```

You should see your changes.

Important: Don't commit these changes yet. We'll continue practising.

### Remember

| Command | Purpose |
| --- | --- |
| `git diff` | Shows unstaged changes |
| `git diff --staged` | Shows staged changes |

## 8. `git show`



## 9. `git restore`

Restore file changes.
Discards unwanted changes in a file and brings it back to its previous committed version.

### Step-by-step practical implementation

Step 1. Open your project

Open `index.html` in VS Code.

Step 2. Modify the file

Change your heading to:

```html
<h1>I am practising Git restore command</h1>
```

Save the file.

Step 3. Check the file status

Run:

```bash
git status
```

You should see:

```bash
Changes not staged for commit:
  modified: index.html
```

Step 4. Execute the restore command

Run:

```bash
git restore index.html
```

Step 5. Verify the result

Open `index.html`.

Your previous committed heading should be restored:

```html
<h1>Learning Git Commands</h1>
```

The exact content will depend on what was saved in your last commit.

Step 6. Check the status again

Run:

```bash
git status
```

You should see:

```bash
nothing to commit, working tree clean
```

Changes restored\!### Important: Another useful variation

Suppose you have already staged a file using `git add`, but you want to remove it from staging without deleting its contents.

Run:

```bash
git restore --staged index.html
```

This unstages the file but keeps your modifications.

### Remember

| Command | Purpose |
| --- | --- |
| `git restore index.html` | Discards unstaged changes |
| `git restore --staged index.html` | Removes file from staging but keeps changes |

Important `git restore index.html` can permanently discard your uncommitted changes. Use it carefully.

## 10. `git reset`

Reset HEAD or staging changes.
Moves files out of the staging area or moves your current branch back to an earlier commit.

### Step-by-step practical implementation

Let's first practise the safe version: removing a file from staging.

Step 1. Open your project

Open `index.html` in VS Code.

Step 2. Modify the file

Add another heading:

```html
<h1>Learning Git Reset</h1>
```

Save the file.

Step 3. Stage the file

Run:

```bash
git add index.html
```

Step 4. Check the status

Run:

```bash
git status
```

You should see:

```bash
Changes to be committed:
  modified: index.html
```

Step 5. Execute the reset command

Run:

```bash
git reset HEAD index.html
```

This removes `index.html` from staging.

Step 6. Verify the result

Run:

```bash
git status
```

You should now see:

```bash
Changes not staged for commit:
  modified: index.html
```

Successfully unstaged\!Your file modifications are still there. They have not been deleted.

### Other useful variations

| Command | Purpose |
| --- | --- |
| `git reset HEAD index.html` | Unstage a specific file |
| `git reset` | Unstage all staged changes |
| `git reset --soft HEAD~1` | Undo the latest commit but keep changes staged |
| `git reset --hard HEAD~1` | Undo the latest commit and discard tracked changes |

Important Avoid `git reset --hard` while learning. It can permanently discard work.

### Remember the difference

- `git restore` → Discards file modifications or unstages files.
- `git reset` → Moves HEAD or removes files from staging, depending on the option.

## 11. `git revert`

Undo changes through a new commit.
Reverses the changes made by an earlier commit without deleting that commit from Git history.

### Step-by-step practical implementation

Step 1. Check your commit history

Run:

```bash
git log --oneline
```

You should see something similar to:

```bash
a1b2c3d Update heading
d4e5f6g Initial commit
```

Step 2. Choose a commit to revert

For practice, choose the `Update heading` commit.

Copy its commit ID.

Step 3. Execute the revert command

Run:

```bash
git revert COMMIT_ID
```

Replace `COMMIT_ID` with the actual ID.

Step 4. Complete the revert

Git may open a text editor asking for a commit message.

- Keep the default revert message.
- Save and close the editor.

Alternatively, use:

```bash
git revert --no-edit COMMIT_ID
```

Step 5. Check the result

Run:

```bash
git status
```

Then:

```bash
git log --oneline
```

You should see a new commit with a message similar to:

```bash
Revert "Update heading"
```

Step 6. Check your file

Open `index.html`.

The changes introduced by the reverted commit should now be undone.

### Remember

| Command | Purpose |
| --- | --- |
| `git revert COMMIT_ID` | Reverses a particular commit |
| `git revert --no-edit COMMIT_ID` | Reverts without opening the commit message editor |

### Important difference

- `git reset` → Moves the branch pointer to another commit.
- `git revert` → Creates a new commit that reverses previous changes.

Note: If you have uncommitted changes, commit or safely set them aside before practising revert.

## 12. `git rm`

Remove tracked files.

Deletes a tracked file from your project and stages its removal for the next commit.

### Step-by-step practical implementation

Step 1. Create a new file

Inside your project, create:

```text
old-file.txt
```

Step 2. Add some content

```text
This is a file I want to delete.
```

Save the file.

Step 3. Add the file to Git

Run:

```bash
git add old-file.txt
```

Step 4. Commit the file

Run:

```bash
git commit -m "Add old file"
```

Now Git is tracking this file.

Step 5. Remove the file

Run:

```bash
git rm old-file.txt
```

Step 6. Check the status

Run:

```bash
git status
```

You should see:

```bash
Changes to be committed:
  deleted: old-file.txt
```

Step 7. Commit the deletion

Run:

```bash
git commit -m "Remove old file"
```

Step 8. Verify the result

Run:

```bash
git status
```

You should see:

```bash
nothing to commit, working tree clean
```

File successfully removed\!### Other useful variations

| Command | Purpose |
| --- | --- |
| `git rm old-file.txt` | Deletes the file and stages deletion |
| `git rm --cached old-file.txt` | Removes file from Git tracking but keeps it on your computer |
| `git rm -r folder-name` | Removes a tracked folder and its contents |

Important: `git rm` removes the file from your working directory too. Commit the deletion to save that change in Git history.

## 13. `git mv`

Rename or move tracked files.

Renames a file or moves it to another folder and automatically stages the change.

### Step-by-step practical implementation

Step 1. Create a new file

Inside your project, create:

```text
old.txt
```

Step 2. Add some content

```text
I am learning Git mv command.
```

Save the file.

Step 3. Start tracking the file

Run:

```bash
git add old.txt
```

Step 4. Commit the file

Run:

```bash
git commit -m "Add old text file"
```

Step 5. Rename the file

Run:

```bash
git mv old.txt new.txt
```

Git renames `old.txt` to `new.txt` and stages the change.

Step 6. Check the status

Run:

```bash
git status
```

You should see something similar to:

```bash
Changes to be committed:
  renamed: old.txt -> new.txt
```

Step 7. Commit the rename

Run:

```bash
git commit -m "Rename old.txt to new.txt"
```

Step 8. Verify the result

Check your project folder.

You should now have:

```text
new.txt
```

The old filename should no longer exist.

### Other useful variations

Rename a file:

```bash
git mv old.txt new.txt
```

Move a file into another folder:

```bash
git mv new.txt documents/new.txt
```

Make sure the `documents` folder already exists.

### Remember

- `git mv` renames or moves a tracked file.
- It automatically stages the change.
- You still need `git commit` to save the change in Git history.

## 14. `git stash`

Temporarily save changes.

Temporarily stores your uncommitted changes so you can work on something else without committing them.

### Step-by-step practical implementation

Step 1. Open your project

Open `index.html` in VS Code.

Step 2. Make some changes

Add this heading:

```html
<h1>Learning Git Stash</h1>
```

Save the file.

Step 3. Check the status

Run:

```bash
git status
```

You should see:

```bash
Changes not staged for commit:
  modified: index.html
```

Step 4. Execute the stash command

Run:

```bash
git stash
```

Git temporarily saves your changes.

Step 5. Verify the result

Run:

```bash
git status
```

You should see:

```bash
nothing to commit, working tree clean
```

Your uncommitted changes are no longer in the working directory.

Step 6. Bring your changes back

Run:

```bash
git stash pop
```

This restores your previously stashed changes and removes that stash entry.

Step 7. Verify your file

Open `index.html`.

You should see your heading:

```html
<h1>Learning Git Stash</h1>
```

Changes restored\!### Other useful variations

| Command | Purpose |
| --- | --- |
| `git stash` | Temporarily save changes |
| `git stash list` | View saved stashes |
| `git stash apply` | Restore changes but keep the stash entry |
| `git stash pop` | Restore changes and remove the stash entry |
| `git stash drop` | Delete a stash entry |

Important: By default, `git stash` saves tracked-file changes. Use `git stash -u` if you also want to stash untracked files.

## 15. `git clean`

Remove untracked files.
Removes files from your project folder that Git is not tracking.

### Step-by-step practical implementation

Step 1. Open your project

Open your Git project in VS Code.

Step 2. Create an untracked file

Create a new file:

```text
temporary.txt
```

Add some content:

```text
This is a temporary file.
```

Save it.

Step 3. Check Git status

Run:

```bash
git status
```

You should see:

```bash
Untracked files:
  temporary.txt
```

Step 4. Preview files that Git would remove

Run:

```bash
git clean -n
```

Expected output:

```bash
Would remove temporary.txt
```

The `-n` option means preview only. It does not delete anything.

Step 5. Actually remove the file

Run:

```bash
git clean -f
```

The `-f` option means force removal.

Step 6. Verify the result

Run:

```bash
git status
```

You should see:

```bash
nothing to commit, working tree clean
```

Also check your project folder. `temporary.txt` should be gone.

Untracked file removed\!### Other useful variations

| Command | Purpose |
| --- | --- |
| `git clean -n` | Preview untracked files to be removed |
| `git clean -f` | Remove untracked files |
| `git clean -fd` | Remove untracked files and directories |
| `git clean -i` | Interactively choose what to remove |

Important `git clean -f` permanently deletes untracked files. Always run `git clean -n` first.

### Remember

- `git rm` → Removes tracked files.
- `git clean` → Removes untracked files.

## 16. `git reflog`

View reference history.

Shows the history of where your Git HEAD and branch references have moved.

### Step-by-step practical implementation

Step 1. Open your project terminal

Make sure you are inside your Git repository.

Step 2. Execute the command

Run:

```bash
git reflog
```

Step 3. Check the output

You should see something similar to:

```bash
a1b2c3d HEAD@{0}: commit: Update heading
d4e5f6g HEAD@{1}: commit: Initial commit
h7i8j9k HEAD@{2}: reset: moving to HEAD~1
```

Step 4. Understand the output

- `HEAD@{0}` → Most recent HEAD position.
- `HEAD@{1}` → Previous HEAD position.
- `commit` → A commit operation.
- `reset` → A reset operation.
- `moving to HEAD~1` → HEAD moved back one commit.

Step 5. View a shorter history

Run:

```bash
git reflog --oneline
```

This displays the reference history in a shorter format.

Step 6. Practise finding a previous commit

Run:

```bash
git reflog
```

Copy an earlier commit ID from the output.

Then run:

```bash
git show COMMIT_ID
```

Replace `COMMIT_ID` with the actual ID.

This lets you inspect that previous commit.

### Remember

| Command | Purpose |
| --- | --- |
| `git reflog` | Displays reference history |
| `git reflog --oneline` | Displays shorter reference history |
| `git show COMMIT_ID` | Inspects a previous commit |

Important: `git reflog` is especially useful when you accidentally move your branch using commands like `git reset`.

## 17. `git config`

Configure Git. Allows you to set your username, email address, and other Git preferences.

### Step-by-step practical implementation

Step 1. Check your current Git username

Run:

```bash
git config --global user.name
```

This displays your configured Git username, if one exists.

Step 2. Set your Git username

Run:

```bash
git config --global user.name "John"
```

Replace `John` with your preferred name.

Step 3. Set your Git email

Run:

```bash
git config --global user.email "john@example.com"
```

Replace this with your own email address.

Step 4. Verify your username

Run:

```bash
git config --global user.name
```

Expected output:

```bash
John
```

Step 5. Verify your email

Run:

```bash
git config --global user.email
```

Expected output:

```bash
john@example.com
```

Step 6. View all your Git configurations

Run:

```bash
git config --list
```

You should see your configured username, email, and other settings.

### Other useful variations

| Command | Purpose |
| --- | --- |
| `git config --global user.name "John"` | Set username globally |
| `git config --global user.email "john@example.com"` | Set email globally |
| `git config --local user.name "John"` | Set username for current repository |
| `git config --list` | View all configurations |
| `git config --global --edit` | Edit global configuration |

### Understand `--global` vs `--local`

- `--global` → Applies to all your Git repositories for your user account.
- `--local` → Applies only to the current Git repository.

## 18. `git help`

Access Git documentation.

Displays instructions and documentation to help you understand how Git commands work.

### Step-by-step practical implementation

Step 1. Open your project terminal

Open the terminal in VS Code.

Step 2. Get general Git help

Run:

```bash
git help
```

This displays general Git documentation and available commands.

Step 3. Get help for a specific command

Run:

```bash
git help commit
```

This opens the documentation explaining the `git commit` command.

Step 4. Try another command

Run:

```bash
git help status
```

This displays documentation for `git status`.

Step 5. Use the quick help option

Run:

```bash
git commit -h
```

This displays a shorter list of options for the commit command directly in your terminal.

### Other useful variations

| Command | Purpose |
| --- | --- |
| `git help` | General Git documentation |
| `git help commit` | Detailed commit documentation |
| `git help status` | Detailed status documentation |
| `git commit -h` | Short command help |
| `git help config` | Configuration documentation |

### Remember

- `git help` → Learn about Git commands.
- `git help COMMAND` → Learn about a specific command.
- `git COMMAND -h` → Get quick command instructions.