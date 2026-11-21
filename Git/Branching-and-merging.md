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

