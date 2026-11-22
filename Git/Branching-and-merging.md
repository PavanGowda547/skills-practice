# 3. Branching and Merging

Branching is essential for working in data engineering teams.

# Branching Concepts

- What is a branch? – A branch is an independent line of development in Git that allows developers to work on code without affecting other branches.
- Why do developers create branches? – Developers create branches to work on new features, bug fixes, or changes independently without disturbing the main codebase.
- Main/Master branch – The main (formerly master) branch contains the stable and production-ready version of the project.
- Feature branches – Feature branches are created to develop new features separately from the main branch.
- Development branches – Development branches are used to integrate and test ongoing development work before merging it into the main branch.
- Bug-fix branches – Bug-fix branches are created to fix bugs in the application without affecting other development work.
- Hotfix branches – Hotfix branches are created to quickly fix critical issues in the production environment.
- Branch naming conventions – Branch naming conventions are standard rules for naming branches, such as `feature/user-login`, `bugfix/data-error`, and `hotfix/production-issue`.
- Creating branches – Creating a branch means starting a new independent line of development using a command like `git branch feature-name`.
- Switching branches – Switching branches means moving from one branch to another using `git switch branch-name`.
- Deleting branches – Deleting a branch means removing a branch that is no longer needed using `git branch -d branch-name`.

# Merging Concepts

- What is merging? – Merging is the process of combining changes from one branch into another branch.
- Fast-forward merge – A fast-forward merge moves the target branch pointer forward when no new commits have been added to the target branch.
- Three-way merge – A three-way merge combines changes from two branches using their common ancestor commit.
- Merge conflicts – Merge conflicts occur when Git cannot automatically combine changes because different branches have modified the same part of a file.
- Resolving merge conflicts – Resolving merge conflicts means manually reviewing conflicting changes, deciding what to keep, and committing the final result.
- Merge vs Rebase – Merge combines branches while preserving their history, whereas rebase moves commits onto another base commit to create a linear history.
- Branch management – Branch management involves creating, naming, switching, merging, updating, and deleting branches to keep team development organized.

<br><br>
Let's explore each concepts with simple easy steps and examples:


## Concept 1: What is a Branch in Git?

A branch is an independent line of development in Git.

It allows developers to work on changes without affecting the original code.

Example:

Imagine you are working on a data engineering project.

Your main project has a Python script that loads data into a database.

Now, you want to add a new feature to clean the data before loading it.

Instead of changing the main code directly, you create a new branch and make your changes there.

Git & GitHub Workshop - Git Guide

[gitguide.acmbpdc.org](<https://gitguide.acmbpdc.org/workshop/?utm_source=chatgpt.com>)

- `main` branch → Contains the existing stable code.
- `feature-data-cleaning` branch → Where you develop the new data-cleaning feature.

Your changes won't affect the `main` branch while you are working on your feature branch.

In simple words: A branch is like creating a separate workspace where you can safely make changes without disturbing the original project.


## Concept 2: Why do developers create branches?

Developers create branches to work on different tasks independently without disturbing the main project.

Example:

Imagine your data engineering team is working on a project.

- Developer 1 → Creates a feature to clean raw data.
- Developer 2 → Creates a feature to load data into Snowflake.
- Developer 3 → Fixes a bug in the existing Python script.

Each developer works on a separate branch.

This allows everyone to work simultaneously without interfering with each other's code.

In simple words: Branches help multiple developers work on different tasks at the same time safely.

## Concept 3: Main/Master Branch

The main branch is the primary branch of a Git project. It usually contains stable, tested code that is ready for production.

Earlier, Git projects commonly used the name `master`. Nowadays, `main` is the more common name.

Example:

Imagine your data engineering project has a pipeline that extracts data from APIs and loads it into a database.

- `main` → Contains the stable, working data pipeline.
- Developers create other branches to add new features or fix bugs.
- After testing and approval, their changes are merged into `main`.

What is Git merge and how does it work?

[graphite.dev](<https://graphite.dev/guides/git-merge-how-does-it-work?utm_source=chatgpt.com>)

In simple words: The main branch contains the primary version of your project that should remain stable.


## Concept 4: Feature Branches

A feature branch is a separate branch created to develop a new feature without changing the main branch.

Example:

Imagine your data engineering project already loads customer data into a database.

Now, your manager asks you to add a new feature that removes duplicate customer records.

You create a feature branch:

```bash
git branch feature/remove-duplicates
```

You develop and test the duplicate-removal logic in this branch.

Once everything works correctly, you merge it into the `main` branch.

In simple words: A feature branch is used to develop a new functionality separately from the main project.


## Concept 5: Development Branches

A development branch is used to combine and test ongoing development work before merging it into the main branch.

Example:

Imagine three developers are working on a data engineering project:

- Developer 1: Working on data extraction.
- Developer 2: Working on data cleaning.
- Developer 3: Working on data loading.

Their completed changes can be merged into a `develop` branch.

The team tests everything together in the `develop` branch before merging it into `main`.

The Git Workflow That Changed How Our Team Ships Code | by Noah Byteforge | Feb, 2026 | Medium

[medium.com](<https://medium.com/%40noahblogwriter2025/the-git-workflow-that-changed-how-our-team-ships-code-d489120250dd?utm_source=chatgpt.com>)

In simple words: A development branch is an integration and testing area where developers combine their work before it goes into the main branch.

Remember:

- `main` → Stable code.
- `develop` → Ongoing development and testing.
- `feature` → Developing individual new features.

## Concept 6: Bug-fix Branches

A bug-fix branch is created to fix an error or problem in an application without disturbing other development work.

Example:

Imagine your data pipeline is processing customer data, but you discover that some customer records are missing their email addresses because of a coding error.

You create a bug-fix branch:

```bash
git branch bugfix/missing-emails
```

You fix the issue and test the code in this branch.

Once the fix is ready, you merge it into the appropriate branch.

In simple words: A bug-fix branch is used to correct existing problems in an application separately from other development work.

Remember:

- Feature branch → Add something new.
- Bug-fix branch → Fix something that is broken.

## Concept 7: Hotfix Branches

A hotfix branch is created to quickly fix a critical issue in the production environment.

A hotfix is more urgent than a normal bug fix because it affects users or business operations.

Example:

Imagine your company's data pipeline runs every hour in production.

Suddenly, the pipeline stops loading data because of a critical error.

Your team creates a hotfix branch:

```bash
git branch hotfix/production-pipeline
```

The developer fixes the issue, tests it, and merges the fix into the production branch.

In simple words: A hotfix branch is used to quickly fix serious problems in a live production system.

Remember the difference:

- Bug-fix branch → Fixes normal bugs.
- Hotfix branch → Fixes urgent, critical production issues.


## Concept 8: Branch Naming Conventions

Branch naming conventions are standard rules that developers follow when naming Git branches.

They help team members understand the purpose of a branch just by looking at its name.

Example:

Imagine your data engineering team creates different branches:

| Branch name | Purpose |
| --- | --- |
| `feature/user-login` | Develop a new login feature |
| `bugfix/data-error` | Fix a data-related bug |
| `hotfix/etl-failure` | Fix a critical ETL issue |
| `develop` | Integrate ongoing development work |

Why is it important?

Suppose you see a branch named `hotfix/etl-failure`.

You immediately understand that it is created to fix an urgent ETL problem.

In simple words: Branch naming conventions are common rules for giving meaningful and understandable names to branches.

## Concept 9: Creating Branches

Creating a branch means starting a new, independent line of development in Git.

We use the following command:

```bash
git branch feature-name
```

Example:

Suppose you are working on a data engineering project and want to develop a new feature to remove duplicate records.

You create a branch:

```bash
git branch feature/remove-duplicates
```

Git creates a new branch called `feature/remove-duplicates`.

Important: This command only creates the branch. It does not automatically switch you to it.

To check your branches, use:

```bash
git branch
```

The `*` symbol indicates your current branch.

In simple words: Creating a branch means creating a separate workspace where you can develop new changes without affecting other branches.

## Concept 10: Switching Branches

Switching branches means moving from one branch to another branch in Git.

We use this command:

```bash
git switch branch-name
```

Example:

Suppose you are currently working on the `main` branch.

You already created a branch called `feature/data-cleaning`.

Now you want to start working on that feature.

Run:

```bash
git switch feature/data-cleaning
```

Now you are working on the `feature/data-cleaning` branch instead of `main`.

Important: Switching branches does not create a new branch. It simply moves you to an existing branch.

In simple words:

- `git branch` → Creates a branch.
- `git switch` → Moves to an existing branch.

## Concept 11: Deleting Branches

Deleting a branch means removing a branch that is no longer needed.

Once a feature or bug fix is completed and merged, the branch can usually be deleted to keep the repository clean.

We use this command:

```bash
git branch -d branch-name
```

Example:

Suppose you created a branch called `feature/data-cleaning`.

You completed the feature and merged it into `main`.

Now you no longer need that branch.

Run:

```bash
git branch -d feature/data-cleaning
```

Git deletes the branch.

Important:

- `-d` → Safely deletes a branch if Git considers it fully merged.
- `-D` → Force deletes a branch, even if it has unmerged changes. Use carefully.

In simple words: Deleting a branch means removing an unnecessary branch after its work is completed.

Correct\!Option A is correct.

`git branch -d feature-name` safely deletes a branch that has been merged.

Branching Concepts Completed\!Great work\! You've completed all 11 branching concepts.

Let's move to the next section.


# Merging Concepts

## Concept 12: What is Merging?

Merging is the process of combining changes from one branch into another branch.

It allows developers to bring their completed work into the main project.

Example:

Imagine you have two branches:

- `main` → Contains the existing data pipeline.
- `feature/data-cleaning` → Contains your newly developed data-cleaning functionality.

After completing and testing your feature, you want to add it to the main branch.

You run:

```bash
git switch main
git merge feature/data-cleaning
```

Now the changes from `feature/data-cleaning` are combined into `main`.

What is Git merge and how does it work?

[graphite.dev](<https://graphite.dev/guides/git-merge-how-does-it-work?utm_source=chatgpt.com>)

In simple words: Merging means bringing changes from one branch into another branch.

Remember:

- Branching → Separating development work.
- Merging → Combining development work.

## Concept 13: Fast-Forward Merge

A fast-forward merge happens when the target branch has no new commits since the feature branch was created.

In this situation, Git simply moves the target branch pointer forward to the latest commit.

Example:

Imagine your Git project has this history:

Git Merge (fast-forward, 3-way, squash, rebase) | Minoolian’s Dev

[minoolian.github.io](<https://minoolian.github.io/tech/Merge.html?utm_source=chatgpt.com>)

1. You create a feature branch from `main`.
2. You add two commits to the feature branch.
3. Nobody makes any new commits to `main`.
4. You merge the feature branch into `main`.

Git simply moves the `main` pointer forward. No extra merge commit is required.

Command:

```bash
git switch main
git merge feature/data-cleaning
```

In simple words: Fast-forward merge means Git moves the main branch pointer forward because there are no new changes on the main branch that need combining.

## Concept 14: Three-Way Merge

A three-way merge happens when two branches have made separate commits after branching from a common ancestor.

Git looks at three points:

1. Common ancestor – The commit where both branches originally shared the same history.
2. Main branch – The latest changes in the main branch.
3. Feature branch – The latest changes in the feature branch.

Git uses these three points to combine the changes.

Example:

Imagine your data engineering project:

- `main` branch → You updated the database connection.
- `feature` branch → Another developer added data-cleaning logic.
- Both branches started from the same earlier commit.

Now you merge the feature branch into main.

Git compares the common ancestor and both branches to combine their changes.

Git basics — lenordsNet

[lenord.me](<https://lenord.me/posts/git_intro/?utm_source=chatgpt.com>)

In simple words: Three-way merge means Git combines changes from two branches by comparing their latest commits with their common starting point.

Remember the difference:

- Fast-forward merge → Simply moves the branch pointer forward.
- Three-way merge → Combines changes using a common ancestor and creates a merge commit.


## Concept 15: Merge Conflicts

A merge conflict happens when Git cannot automatically combine changes from two branches.

This usually happens when two developers modify the same part of a file differently.

Example:

Imagine two developers are working on the same Python ETL script.

- Developer 1 changes the database name to `customer_db`.
- Developer 2 changes the database name to `sales_db`.

Both developers modify the same line in different branches.

When you try to merge those branches, Git cannot decide which database name to keep.

This is called a merge conflict.

Git marks the conflicting section so you can review it.

In simple words: A merge conflict happens when Git finds different changes in the same part of a file and needs a developer to decide what to keep.

## Concept 16: Resolving Merge Conflicts

Resolving merge conflicts means manually reviewing conflicting changes and deciding which changes should remain in the final code.

Example:

Imagine two developers modified the same line in a Python ETL script.

Developer 1:

```python
database = "customer_db"
```

Developer 2:

```python
database = "sales_db"
```

When merging, Git cannot decide which value to keep.

You open the file and see something like:

```python
<<<<<<< HEAD
database = "customer_db"
=======
database = "sales_db"
>>>>>>> feature-branch
```

You review the code and decide which value is correct.

For example, you keep:

```python
database = "customer_db"
```

Then you remove the conflict markers, save the file, and complete the merge.

In simple words: Resolving a merge conflict means reviewing different changes, choosing the correct code, and completing the merge.

Remember the basic steps:

1. Identify the conflicting file.
2. Review both changes.
3. Decide what code to keep.
4. Save the file and complete the merge.

## Concept 17: Merge vs Rebase

Merge and Rebase are two different ways to combine changes from different branches in Git.

### 1. Merge

Merge combines changes from two branches while preserving their existing commit history.

Example:

You have:

- `main` → Contains database connection changes.
- `feature` → Contains data-cleaning changes.

You merge the feature branch into main:

```bash
git switch main
git merge feature
```

Git combines the changes and preserves the branch history.

### 2. Rebase

Rebase moves your feature branch commits onto the latest commit of another branch.

Example:

Your colleague updated the `main` branch, and you want your feature branch to start from those latest changes.

You run:

```bash
git switch feature
git rebase main
```

Git replays your feature commits on top of the latest main branch commit.

Git Merge vs Git Rebase (A Beginner Perspective) | by Arya | Feb, 2026 | Medium

[arvita-writes.medium.com](<https://arvita-writes.medium.com/git-merge-vs-git-rebase-a-beginner-perspective-f91f44ed1c74?utm_source=chatgpt.com>)

### Main difference

| Merge | Rebase |
| --- | --- |
| Preserves existing branch history | Creates a more linear history |
| May create a merge commit | Replays commits onto a new base |
| Does not rewrite existing commits | Rewrites commit history |

In simple words:

- Merge → Combines branches and preserves their history.
- Rebase → Moves your commits onto another base to create a cleaner, linear history.

Important: Avoid rebasing shared branches that other developers are already using, because rebase rewrites commit history.

Correct\!Option B is correct.

Rebase creates a more linear commit history by replaying commits onto another base.

## Concept 18: Branch Management

Branch management means organizing and maintaining Git branches throughout a project.

It includes:

- Creating branches.
- Naming branches properly.
- Switching between branches.
- Merging completed work.
- Updating branches.
- Deleting branches that are no longer needed.

Example:

Imagine you are working in a data engineering team.

Your team has these branches:

```text
main
develop
feature/data-cleaning
bugfix/duplicate-records
hotfix/etl-failure
```

Your team follows this process:

1. Create a feature branch for new functionality.
2. Develop and test the code.
3. Merge completed work into the development branch.
4. Test the combined changes.
5. Merge stable changes into main.
6. Delete unnecessary branches.

This entire process is called branch management.

In simple words: Branch management means keeping Git branches properly organized so that multiple developers can work together efficiently.