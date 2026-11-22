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

