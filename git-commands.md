# Git Commands Guide

## 1. Repository Initialization & Setup

### 1.1 Initialize a Git Repository

**`git init`**

```bash
git init  # Creates a .git directory in the current folder
```

- Initializes a new Git repository in the current directory.

- Creates a `.git` folder to track changes.

**`git init --initial-branch=main`**

```bash
git init --initial-branch=main  # Sets the default branch name to "main"
```

- Initializes the repository with `main` as the default branch instead of `master`.

### 1.2 Clone a Repository

**`git clone <repository-url>`**

```bash
git clone https://github.com/user/repo.git  # Clones into a folder named "repo"
```

- Creates a local copy of an existing remote repository.

**`git clone <url> <folder>`**

```bash
git clone https://github.com/user/repo.git my-folder  # Clones into "my-folder"
```

- Clones the repository into a specific folder.

## 2. Basic Workflow

### 2.1 Checking Repository Status

**`git status`**

```bash
git status  # Outputs:
# On branch main
# Changes not staged for commit: modified: file.txt
```

- Shows the current state of the working directory (untracked/modified/staged files).

### 2.2 Staging and Committing

**`git add`**

```bash
git add file.txt       # Stages a specific file
git add .              # Stages all changes in the current directory
git add folder/        # Stages all changes in "folder"
```

- Stages specific files or all changes for commit..

**`git commit`**

```bash
git commit -m "Add feature"  # Commits staged changes with a message
git commit --amend           # Edit the previous commit message or add missed files
git commit --amend --reset-author  # Update commit author details or Changes the author of the last commit.
```

- Save staged changes to the repository.

```bash
git add . + git commit -m "Commit message"
```

- Combination of `git add .` and `git commit -m "Commit message"`

## 3. Viewing Commit History

**`git log`**

```bash
git log               # Shows full commit history
git log --all --graph # Visualize branches and merges or Displays a visual commit graph.
```

## 4. Branching & Merging

### 4.1 Creating and Switching Branches

**`git branch`**

```bash
git branch  # Lists all local branches.
```

**`git branch <branch-name>`**

```bash
git branch new-feature      # Create a new branch --> 'new-feature'
```

**`git checkout -b <branch-name>`**

```bash
git checkout -b dev    # Create and switch to "dev" branch
```

- Creates and switches to a new branch.

**`git checkout <branch-name>`**

```bash
git checkout main           # Switch to the "main" branch
```

- Switches to an existing branch.

**`git switch <branch-name>`**

```bash
git switch dev    # Modern alternative to `git checkout dev`
```

- Modern alternative to `checkout`, recommended for switching branches.

**`git checkout -- <file-name>`**

**_Discard changes to a single file_**

- Discard **unstaged changes** in a specific file, reverting it to the state of the last commit (or the state in the staging area if the file is staged).

- This command is a "undo" for local modifications that haven’t been committed yet.

```bash
git checkout -- index.html  # Revert index.html to its last committed state
```

- Restores a file to its last committed state.

**`git checkout <branch-name> <file-name>`**

```bash
git checkout main file.txt
```

- Restores a file from a specific branch.

**Key Notes**

- The **`--`** is used to clarify that **`<file>`** is a file path (not a branch name).

- This is important if your file has the same name as a branch (e.g., **`git checkout -- main`** ).

- **Does NOT affect staged changes.** If the file is staged, use **`git reset HEAD <file>`** first to unstage it.

- **Irreversible:** Discarded changes cannot be recovered unless you have a backup.

**`git checkout --`**

**_Discard changes to all files in the current directory:_**

```bash
git checkout -- .  # Revert all files in the current directory to its last committed state
```

- Restores all files in the current directory to its last committed state

**`git checkout -- <deleted-file-name>`**

**_Recovers a deleted file (if it was tracked):_**

```bash
git checkout -- deleted-file.txt  # Restores the deleted file
```

**`git restore <deleted-file-name>`**

```bash
git restore index.html  # Equivalent to `git checkout -- index.html`
```

Modern alternatives of `git checkout -- <deleted-file-name>`

**`git checkout <commit-hash>`**

```bash
git checkout 8a3b1c2   # Switch to a specific commit (detached HEAD)
```

- Moves to a specific commit in history.

### 4.2 Deleting Branches

**`git branch -r`**

```bash
git branch -r               # List remote branches
```

- Lists remote branches.

**`git branch -d <branch-name>`**

```bash
git branch -d old-feature   # Delete a merged branch
```

- Deletes a branch (only if merged).

**`git branch -D <branch>`**

```bash
git branch -D broken-branch # Force delete an unmerged branch
```

- Forces branch deletion (even if unmerged).

### 4.3 Merging and Rebasing

**`git merge <branch-name>`**

```bash
git checkout main
git merge dev  # Merges "dev" into "main"
```

- Merges another branch into the current one.

**`git rebase`**

```bash
git checkout feature
git rebase main  # Move "feature" commits to the tip of "main"
```

- Moves the base of the branch to the latest commit of the target branch.

- Reapply commits on top of another branch (rewrites history).

**`git rebase -i`**

```bash
git rebase -i HEAD~3
```

- Interactive rebase (useful for modifying commits).

## 5. Working with Remote Repositories

### 5.1 Pushing Changes

**`git push`**

```bash
git push     # Push to the default remote/branch
```

- Pushes changes to the remote repository.

**`git push <remote> <branch>`**

```bash
git push origin main          # Push "main" to "origin"
```

- Pushes a specific branch to a remote.

```bash
git push -u origin new-feature # Set upstream (tracking) branch
```

- Pushes a new branch and sets it as the upstream.

```bash
git push -f       # Force push (use with caution!)
git push --force  # Force push (use with caution!)
```

- Force-pushes changes (use with caution, as it overwrites history).

### 5.2 Fetching and Pulling

**_Download changes from a remote._**

**`git fetch`**

```bash
git fetch origin    # Fetch changes from "origin" without merging
```

- Retrieves changes from the remote repository without merging.

**`git pull / git pull <remote> <branch>`**

```bash
git pull
git pull origin main # Fetch + merge changes from "origin/main"
```

- Fetches and merges changes in one step.

### 5.3 Managing Remotes

**`git remote`**

```sh
git remote
```

- Lists remote repositories.

**`git remote add origin <repository-url>`**

```bash
git remote add origin https://github.com/user/repo.git  # Add a remote
```

- Links the local repository to a remote.

```bash
git remote -v    # List remotes with URLs
```

- Shows the remote repository URL.

**`git remote remove <name>`**

```bash
git remote remove origin      # Removes a remote
```

```bash
git remote show origin  # Show details about "origin"
```

- Displays details about a remote.

```sh
git remote get-url origin          # Get the URL of "origin"
git config --get remote.origin.url # Get the URL of "origin"
```

- Shows the URL of the remote repository.

**`git remote set-url origin <url>`**

```bash
git remote set-url origin git@github.com:username/repo.git        # for https
git remote set-url origin git@github-username:username/repo.git  # for ssh
```

- Reset or changes the remote URL.

**`git config --global url."<new-url>".insteadOf "<old-url>"`**

```bash
git config --global url."git@github-hameed003:".insteadOf "git@github.com:hameed003/"
```

- URL substitution for SSH.

## 6. Stashing & Resetting

### 6.1 Stashing Changes

**`git stash`**

```bash
git stash           # Save changes to a stash
git stash pop       # Reapply the most recent stash
```

- Temporarily saves uncommitted changes.

### 6.2 Resetting & Reverting

**`git reset`**

```bash
git reset file.txt     # Unstage "file.txt"
git reset --hard HEAD~3  # Discard last 3 commits and all changes (destructive!)
```

- Unstages changes without deleting them.

**`git reset --hard <commit-hash>`**

```bash
git reset --hard abc123
```

- Resets the repository to a specific commit (deletes all newer changes).

**`git revert / git revert <commit-hash>`**

```bash
git revert abc123  # Revert the commit with hash "abc123"
```

- Creates a new commit that undoes a specific commit.

## 7. Viewing Differences

**`git diff`**

- Shows the **unstaged changes** (modifications in the working directory that are not yet staged).
- It helps you see what changes have been made before staging them.

```bash
git diff
```

- Displays differences between the working directory and the last committed version.

**`git diff --staged`**

- Shows **staged changes** (modifications that have been added with git add but not yet committed).
- Helps review changes that will be included in the next commit.

```bash
git diff --staged
```

- Displays the differences between the staged version and the last committed version.

| Command             | Shows Differences Between       |
| ------------------- | ------------------------------- |
| `git diff`          | Working directory ↔ Last commit |
| `git diff --staged` | Staged changes ↔ Last commit    |

```bash
git stats
```

- Displays repository statistics.

## 8. Removing & Ignoring Files

**`git rm`**

```bash
git rm file.txt      # Delete and stage the deletion
```

- Removes a file from tracking and deletes it.

**`git rm --cached`**

```bash
git rm --cached file.txt # Untrack the file (keeps it locally)
```

- Removes a file from Git but keeps it locally.

**`rm -rf .git`**

```bash
rm -rf .git  # Removes all version control history
```

- ⚠️ WARNING: Deletes the entire Git history. or Delete the Git repository (irreversible!).

# **`.gitignore`**

```bash
# .gitignore
*.log
node_modules/
```

- Specifies files to be ignored by Git.

## 9. Git Configuration

```bash
git config user.name "John Doe"                       # Set local or per-repo username
git config user.email "jhondoe@gmail.com"            # Set local or per-repo email .

git config --global user.name "John Doe"            # Set global username
git config --global user.email "john@example.com"  # Set global email
```

```bash
git config --list           # Show all settings
git config --local --list  # Show local settings
```

- Lists all Git configurations.

```bash
git config --show-origin --list
```

- Show config file locations.

**`git config --global alias.<shortcut> <command>`**

```bash
git config --global alias.s status  # Create shortcut: `git s`
git config --global alias.co "checkout" # Create shortcut: `git co`
```

- Creates a shortcut for a Git command.

```bash
git config --unset user.name             # Remove a local setting
git config --global --unset user.email  # Remove a global setting
```

## 10. Tagging & Submodules

```bash
git tag
```

- Lists available tags.

```bash
git tag v1.0.0          # Create a lightweight tag
```

**`git tag -a v1.0.0 -m "Release version"`**

```bash
git tag -a v1.0 -m "Version 1.0"   # Create an annotated tag
```

- Creates an annotated tag for versioning.

**`git submodule add <url>`**

```bash
git submodule add https://github.com/user/library.git  # Adds a submodule
```

- Adds a submodule (nested repository inside a repository). or Embeds another repository as a subdirectory.

## 11. Advanced Git Commands

```bash
git reflog
```

- Displays history of reference changes.

**`git cherry-pick <commit-hash>`**

```bash
git cherry-pick abc123  # Apply commit "abc123" to the current branch
```

Applies a specific commit to the current branch.

**`git bisect`**

```bash
git bisect start
git bisect bad   # Mark current commit as faulty
git bisect good v1.0  # Mark a known good commit
```

- Uses binary search to find a problematic commit.

**`git mv <old-file> <new-file>`**

```bash
git mv old.txt new.txt  # Rename and stage the change
```

- Renames or moves a file.

## 12. Getting Help

**`git help / git help commit / git <command> --help`**

```sh
git help
git help commit     # Open manual for `git commit`
git checkout --help # Display help for `git checkout`
```

Displays detailed help for a command.

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
