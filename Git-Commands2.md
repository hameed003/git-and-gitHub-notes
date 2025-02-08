# Git Commands Cheat Sheet

A comprehensive list of Git commands organized by category.

---

## 1. Repository Setup & Configuration

| Command                          | Explanation                                 | Example                                                 |
| -------------------------------- | ------------------------------------------- | ------------------------------------------------------- |
| `git init`                       | Initialize a new Git repository.            | `git init`                                              |
| `git init --initial-branch=main` | Initialize with a specific default branch.  | `git init --initial-branch=main`                        |
| `git clone <url>`                | Clone a remote repository.                  | `git clone https://github.com/user/repo.git`            |
| `git clone <url> <folder>`       | Clone into a specific folder.               | `git clone https://github.com/user/repo.git my-project` |
| `rm -rf .git`                    | **⚠️ Delete Git tracking** (irreversible!). | `rm -rf .git`                                           |

---

## 2. Basic Configuration

| Command                                          | Explanation                 | Example                                               |
| ------------------------------------------------ | --------------------------- | ----------------------------------------------------- |
| `git config --global user.name "Name"`           | Set global username.        | `git config --global user.name "Hameed008"`           |
| `git config --global user.email "email"`         | Set global email.           | `git config --global user.email "hameed@example.com"` |
| `git config user.name "Name"`                    | Set per-repo username.      | `git config user.name "Hameed009"`                    |
| `git config user.email "email"`                  | Set per-repo email.         | `git config user.email "hameed009@example.com"`       |
| `git config --global alias.<shortcut> <command>` | Create a command alias.     | `git config --global alias.s "status"`                |
| `git config --global --get user.name`            | View global username.       | `git config --global --get user.name`                 |
| `git config --global --unset user.name`          | Remove global username.     | `git config --global --unset user.name`               |
| `git config --list`                              | List all configurations.    | `git config --list`                                   |
| `git config --show-origin --list`                | Show config file locations. | `git config --show-origin --list`                     |

---

## 3. Staging & Committing

| Command                   | Explanation                 | Example                                       |
| ------------------------- | --------------------------- | --------------------------------------------- |
| `git add <file\|folder>`  | Stage changes.              | `git add .` (stage all)<br>`git add file.txt` |
| `git commit -m "message"` | Commit staged changes.      | `git commit -m "Add feature"`                 |
| `git commit --amend`      | Modify the previous commit. | `git commit --amend -m "Updated message"`     |
| `git reset <file>`        | Unstage changes.            | `git reset file.txt`                          |
| `git checkout -- <file>`  | Discard unstaged changes.   | `git checkout -- file.txt`                    |

---

## 4. Branch Management

| Command                    | Explanation                    | Example                                 |
| -------------------------- | ------------------------------ | --------------------------------------- |
| `git branch`               | List all branches.             | `git branch`                            |
| `git branch <name>`        | Create a new branch.           | `git branch feature1`                   |
| `git checkout <branch>`    | Switch to a branch.            | `git checkout main`                     |
| `git checkout -b <branch>` | Create and switch to a branch. | `git checkout -b new-feature`           |
| `git branch -D <branch>`   | **Force-delete a branch**.     | `git branch -D old-feature`             |
| `git merge <branch>`       | Merge a branch into current.   | `git merge feature1 -m "Merge message"` |

---

## 5. Remote Repositories

| Command                                                     | Explanation                       | Example                                                                                 |
| ----------------------------------------------------------- | --------------------------------- | --------------------------------------------------------------------------------------- |
| `git remote add <name> <url>`                               | Add a remote repository.          | `git remote add origin https://github.com/user/repo.git`                                |
| `git remote -v`                                             | List remotes with URLs.           | `git remote -v`                                                                         |
| `git remote remove <name>`                                  | Remove a remote.                  | `git remote remove origin`                                                              |
| `git push <remote> <branch>`                                | Push to a remote branch.          | `git push origin main`                                                                  |
| `git push -u <remote> <branch>`                             | Set upstream branch.              | `git push -u origin feature1`                                                           |
| `git push -f`                                               | **Force-push** (use cautiously!). | `git push origin main -f`                                                               |
| `git fetch`                                                 | Fetch remote changes.             | `git fetch origin`                                                                      |
| `git pull <remote> <branch>`                                | Fetch and merge changes.          | `git pull origin main`                                                                  |
| `git remote set-url origin <url>`                           | Change remote URL.                | `git remote set-url origin git@github.com:user/repo.git`                                |
| `git config --global url."<new-url>".insteadOf "<old-url>"` | URL substitution for SSH.         | `git config --global url."git@github-hameed009:".insteadOf "git@github.com:hameed009/"` |

---

## 6. Commit History & Navigation

| Command                        | Explanation                 | Example                           |
| ------------------------------ | --------------------------- | --------------------------------- |
| `git log`                      | View commit history.        | `git log`                         |
| `git log --all --graph`        | Visualize branch history.   | `git log --all --graph --oneline` |
| `git checkout <commit-hash>`   | Inspect a specific commit.  | `git checkout a1b2c3d`            |
| `git checkout <branch> <file>` | Restore file from a branch. | `git checkout main file.txt`      |

---

## 7. Advanced Operations

| Command                             | Explanation             | Example                             |
| ----------------------------------- | ----------------------- | ----------------------------------- |
| `git rebase -i`                     | Interactive rebase.     | `git rebase -i HEAD~3`              |
| `git commit --amend --reset-author` | Fix commit authorship.  | `git commit --amend --reset-author` |
| `git submodule add <url>`           | Add a submodule.        | `git submodule add ../sub-repo`     |
| `git reflog`                        | View reference history. | `git reflog`                        |

---

## 9. Conflict Resolution

| Command                    | Explanation                   | Example                                                                            |
| -------------------------- | ----------------------------- | ---------------------------------------------------------------------------------- |
| `git add .` + `git commit` | Finalize conflict resolution. | After resolving conflicts:<br>`git add .`<br>`git commit -m "Fix merge conflicts"` |

---

## 10. Ignoring Files

| File/Command | Explanation              | Example                                        |
| ------------ | ------------------------ | ---------------------------------------------- |
| `.gitignore` | Specify untracked files. | Add `node_modules/` to ignore Node.js modules. |

---

## Workflow Example

**Feature Branch Workflow:**

```bash
git branch new-feature    # Create branch
git checkout new-feature  # Switch to branch
git switch new-feature    # Modern way to switch a branch

#OR

git checkout -b new-feature    # Create and switch to a new branch

# Make changes, commit, and push:
git add .
git commit -m "Implement new feature"
git push -u origin new-feature # Push to remote

# Later, merge into main:
git checkout main              # Switch to main
git pull origin main           # Sync with remote or Update main
git merge new-feature          # Merge the feature
git push origin main
```
