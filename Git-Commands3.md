# Git Commands Cheat Sheet

A comprehensive list of Git commands with explanations and examples.

---

## 1. Repository Setup

| Command     | Explanation                               | Example                                      |
| ----------- | ----------------------------------------- | -------------------------------------------- |
| `git init`  | Initializes a new Git repository.         | `git init` ( creates a `.git` directory )    |
| `git clone` | Clones an existing repository from a URL. | `git clone https://github.com/user/repo.git` |

---

## 2. Basic Workflow

| Command      | Explanation                             | Example                                                                  |
| ------------ | --------------------------------------- | ------------------------------------------------------------------------ |
| `git add`    | Stages changes for commit.              | `git add file.txt` ( stage a file )<br>`git add .` ( stage all changes ) |
| `git commit` | Saves staged changes to the repository. | `git commit -m "Add feature X"`                                          |
| `git status` | Shows working directory status.         | `git status`                                                             |
| `git log`    | Displays commit history.                | `git log --oneline --graph`                                              |
| `git diff`   | Shows changes between commits/files.    | `git diff` ( unstaged )<br>`git diff --staged` ( staged )                |

---

## 3. Branching & Merging

| Command        | Explanation                          | Example                                                  |
| -------------- | ------------------------------------ | -------------------------------------------------------- |
| `git branch`   | Lists, creates, or deletes branches. | `git branch` ( list )<br>`git branch feature` ( create ) |
| `git checkout` | Switches branches or restores files. | `git checkout feature`<br>`git checkout -b new-feature`  |
| `git merge`    | Merges changes from another branch.  | `git merge feature`                                      |
| `git rebase`   | Reapplies commits on another branch. | `git rebase main`                                        |

---

## 4. Remote Repositories

| Command      | Explanation                        | Example                                                 |
| ------------ | ---------------------------------- | ------------------------------------------------------- |
| `git remote` | Manages remote repositories.       | `git remote -v` ( list )<br>`git remote add origin URL` |
| `git fetch`  | Downloads objects from a remote.   | `git fetch origin`                                      |
| `git pull`   | Fetches and merges remote changes. | `git pull origin main`                                  |
| `git push`   | Uploads local commits to a remote. | `git push -u origin main`                               |

---

## 5. Undoing Changes

| Command       | Explanation                           | Example                                                  |
| ------------- | ------------------------------------- | -------------------------------------------------------- |
| `git reset`   | Unstages changes or resets commits.   | `git reset HEAD~1` ( soft )<br>`git reset --hard HEAD~1` |
| `git revert`  | Creates a commit that undoes changes. | `git revert 1a2b3c`                                      |
| `git restore` | Restores files to a previous state.   | `git restore file.txt`                                   |

---

## 6. Stashing

| Command     | Explanation                            | Example                        |
| ----------- | -------------------------------------- | ------------------------------ |
| `git stash` | Temporarily saves uncommitted changes. | `git stash`<br>`git stash pop` |

---

## 7. Tagging

| Command   | Explanation                              | Example                                          |
| --------- | ---------------------------------------- | ------------------------------------------------ |
| `git tag` | Marks specific commits (e.g., releases). | `git tag v1.0`<br>`git tag -a v1.0 -m "Release"` |

---

## 8. Advanced Commands

| Command           | Explanation                                      | Example                  |
| ----------------- | ------------------------------------------------ | ------------------------ |
| `git cherry-pick` | Applies a specific commit to the current branch. | `git cherry-pick 1a2b3c` |
| `git bisect`      | Binary search to find bugs.                      | `git bisect start`       |
| `git reflog`      | Shows reference changes (e.g., resets).          | `git reflog`             |

---

## 9. Configuration

| Command      | Explanation                     | Example                                    |
| ------------ | ------------------------------- | ------------------------------------------ |
| `git config` | Sets Git configuration options. | `git config --global user.name "John Doe"` |

---

## 10. File Management

| Command  | Explanation                  | Example                  |
| -------- | ---------------------------- | ------------------------ |
| `git rm` | Removes files from tracking. | `git rm file.txt`        |
| `git mv` | Renames or moves files.      | `git mv old.txt new.txt` |

---

## 11. Submodules

| Command         | Explanation                  | Example                                              |
| --------------- | ---------------------------- | ---------------------------------------------------- |
| `git submodule` | Manages nested repositories. | `git submodule add https://github.com/user/repo.git` |

---

## 12. Help

| Command    | Explanation              | Example           |
| ---------- | ------------------------ | ----------------- |
| `git help` | Opens Git documentation. | `git help commit` |

---

### Notes:

- Replace `origin` with your remote name and `main`/`master` with your branch name.
- Use `--force` cautiously ( e.g., `git push --force`).
- For detailed help: `git <command> --help`.
