# 4. Remote Repositories

Understand how local repositories communicate with GitHub.

### Concepts

- [ ] What is a remote repository?
- [ ] Git remote
- [ ] Origin
- [ ] Upstream
- [ ] Remote tracking branches
- [ ] HTTPS authentication
- [ ] SSH authentication
- [ ] SSH keys
- [ ] Personal Access Tokens (PAT)
- [ ] Tracking branches

### Important Commands

| Command | Purpose |
|---|---|
| `git remote` | View remote repositories |
| `git remote -v` | View remote URLs |
| `git remote add` | Add a remote |
| `git fetch` | Download remote updates |
| `git pull` | Fetch and integrate updates |
| `git push` | Upload commits |
| `git push -u origin branch-name` | Set upstream tracking |

<br><br>
Let's explore each concepts with simple easy steps and examples:

## Topic: Connecting Local Git Repositories with GitHub

First, understand the big picture.
There are two important places where your project can exist:
```
Local Repository
Your computer
Where you write and modify code
    |
Push and Pull
Remote Repository
    |
GitHub
Where your project is hosted online
```
For example, you develop a Python ETL pipeline on your laptop. You want to upload your code to GitHub so your teammates can access it.

Git provides commands to communicate between these two repositories.

## Concept 1: What is a Remote Repository?

A remote repository is a version of your Git project that is hosted somewhere outside your local computer, usually on platforms like GitHub.

It allows multiple developers to access and collaborate on the same project.

Example:

Imagine you are developing a data engineering project.

Your local project contains:

```text
data-pipeline/
    extract.py
    transform.py
    load.py
```

You create a repository on GitHub called `data-pipeline`.

Now you have:

- Local repository → Your project stored on your laptop.
- Remote repository → Your project stored on GitHub.

Creating Your First GitHub Repository

[clevertechie.com](<https://clevertechie.com/guides/creating-your-first-github-repository?utm_source=chatgpt.com>)

### How do they communicate?

There are two important operations:

1. Push

Push means sending your local commits to GitHub.

Example:

You modify `transform.py` and commit your changes.

Then:

```bash
git push
```

Your committed changes are uploaded to the remote repository.

2. Pull

Pull means bringing changes from GitHub into your local repository.

Example:

Your teammate updates `load.py` on GitHub.

You run:

```bash
git pull
```

Git downloads and integrates those changes into your local branch.

### Important commands

| Command | Meaning |
| --- | --- |
| `git push` | Upload local commits |
| `git pull` | Download and integrate remote changes |
| `git fetch` | Download remote updates without integrating them |

### Real-world data engineering scenario

Imagine you and your teammate are working on the same ETL project.

1. You update the data extraction logic on your laptop.
2. You commit your changes.
3. You push them to GitHub.
4. Your teammate pulls the latest changes.
5. Your teammate now has your updated extraction logic locally.

This is how developers collaborate using GitHub.

In simple words: A remote repository is your project's online Git repository that allows you and your teammates to share code and collaborate.

## Concept 2: Git Remote

Git remote is a Git command used to manage connections between your local repository and remote repositories such as GitHub.

In simple words, Git remote tells your local Git repository where your online repository is located.

### Example

Imagine you have created a GitHub repository:

`https://github.com/yourname/data-pipeline.git`

You also have the same project on your laptop.

You want to connect your local repository to GitHub.

First, run:

```bash
git remote add origin https://github.com/yourname/data-pipeline.git
```

Let's understand this command:

| Part | Meaning |
| --- | --- |
| `git` | Git command |
| `remote` | Manage remote connections |
| `add` | Add a new remote connection |
| `origin` | Name given to the remote |
| URL | Location of your GitHub repository |

Important: This command connects your local repository to GitHub. It does not upload your files.

### How to check remote connections?

Run:

```bash
git remote -v
```

Example output:

```text
origin  https://github.com/yourname/data-pipeline.git (fetch)
origin  https://github.com/yourname/data-pipeline.git (push)
```

This tells you that your local repository is connected to that GitHub repository.

- `fetch` → Where Git downloads updates from.
- `push` → Where Git uploads your changes.

### Real-world data engineering example

Suppose you are working on a project called `customer-etl`.

You create a GitHub repository for it and connect your local project:

```bash
git remote add origin https://github.com/yourname/customer-etl.git
```

Now Git knows where to send your committed changes when you run:

```bash
git push -u origin main
```

In simple words: Git remote is used to connect and manage the connection between your local repository and an online repository.

## Concept 3: Origin

Origin is the default name Git commonly gives to a remote repository when you clone a repository or when you add a remote using that name.

In simple words, origin is simply a nickname for your GitHub repository.

## Concept 4: Upstream

Upstream is a term used in Git to refer to another repository or branch that your work is based on or follows.

There are two common situations where you'll hear this term.

### 1. Upstream as a remote repository

Imagine you are contributing to an open-source data engineering project.

There are two GitHub repositories:

- Original repository → Belongs to another developer or organization.
- Forked repository → Your own copy of the original repository.

You fork the original project to your GitHub account.

Now you have two remote repositories:
```
Original GitHub repository
upstream
Original project maintained by another team
    |
Fork
    |
Your GitHub repository
originYour personal copy of the project
    |
Clone
    |
Your local repository
Your computer
```
You can configure both remote connections:

```bash
# Your own GitHub repository
git remote add origin https://github.com/yourname/customer-etl.git

# Original developer's repository
git remote add upstream https://github.com/company/customer-etl.git
```

Now check them:

```bash
git remote -v
```

You might see:

```text
origin    https://github.com/yourname/customer-etl.git
upstream  https://github.com/company/customer-etl.git
```

Why do we need upstream?

Suppose the original project gets updated by its maintainers.

You want those latest changes in your local project.

You can run:

```bash
git fetch upstream
```

This downloads the latest updates from the original repository without automatically merging them into your current branch.

You can then integrate the appropriate upstream branch into your work.

### 2. Upstream as a tracking branch

Upstream can also refer to the remote branch that your local branch tracks.

For example, your local `main` branch may track `origin/main`.

This relationship makes commands like `git pull` and `git push` easier because Git knows which remote branch to use by default.

We'll study this properly in the tracking branches concept.

### Remember the difference

| Name | Meaning |
| --- | --- |
| `origin` | Usually your own GitHub repository |
| `upstream` | Usually the original repository you forked from |

Important: These are naming conventions, not special Git keywords. You can choose different remote names.

In simple words: Upstream commonly refers to the original repository from which you got your project, especially when contributing to someone else's project.

## Concept 5: Remote Tracking Branches

This is an important concept because it explains how Git remembers the state of branches on GitHub.

A remote tracking branch is a local reference that represents the state of a branch on a remote repository.

In simple words, it helps your local Git repository remember what the remote branch looked like the last time Git checked for updates.

### Example

Imagine your GitHub repository has a branch called `main`.

On GitHub:

```text
origin/main
```

On your computer, Git maintains a remote tracking reference:

```text
origin/main
```

It represents the last known state of the remote `main` branch.

Remote repositories – Using Git to Code, Collaborate and Share

[imperialcollegelondon.github.io](<https://imperialcollegelondon.github.io/grad_school_git_course/l2-02-remote_repositories/index.html?utm_source=chatgpt.com>)

### Let's understand with a real scenario

Suppose you and your teammate are working on a data engineering project.

Step 1: Initially, both branches are at the same commit.

```text
Local main:    A --- B
Remote main:   A --- B
```

Step 2: Your teammate pushes a new commit to GitHub.

```text
Local main:    A --- B
Remote main:   A --- B --- C
```

Your local repository doesn't automatically know about commit C.

Step 3: You run:

```bash
git fetch origin
```

Now Git downloads the latest remote information.

Your remote tracking branch moves forward:

```text
Local main:    A --- B
origin/main:   A --- B --- C
```

Notice something important:

Your local `main` branch is still at B, but `origin/main` now represents C.

This is the purpose of a remote tracking branch.

### How can you see remote tracking branches?

Run:

```bash
git branch -r
```

Example output:

```text
origin/main
origin/develop
origin/feature/data-cleaning
```

This displays the remote tracking branches known to your local repository.

### Important commands

| Command | Purpose |
| --- | --- |
| `git fetch origin` | Updates remote tracking information |
| `git branch -r` | Lists remote tracking branches |
| `git branch -a` | Lists local and remote tracking branches |

Important: A remote tracking branch is not a separate working branch where you normally write code. It is a reference maintained by Git.

In simple words: A remote tracking branch helps Git remember the latest known state of a branch on GitHub.

