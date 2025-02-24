Repository Setup & Basics
git init
Initialize a new Git repository.

git status
Show changes in the working/staging area.

git config --global user.name "Your Name"
Set global username for commits.

git config --global user.email "email@example.com"
Set global email for commits.

git config --global alias.shortcut <command>
Create a command alias (e.g., git config --global alias.s "status").

Staging & Committing
git add <file|folder>
Stage changes for commit (e.g., git add ., git add file, git add folder/).

git commit -m "message"
Create a commit with a message.

git commit -m "message" --amend
Modify the previous commit.

git reset <file|folder>
Unstage changes (e.g., git reset file, git reset .).

git checkout -- <file|folder>
Discard unstaged changes (e.g., git checkout -- file).

Commit History & Navigation
git log
View commit history.

git log --all
Show all branches' commit history.

git log --all --graph
Visualize branch history.

git checkout <commit_hash|branch_name>
Switch to a specific commit or branch.

git checkout <hash|branch> <file|folder>
Restore files to a previous state (e.g., git checkout master file).

Branching & Merging
git branch <branch_name>
Create a new branch (e.g., git branch feature1).

git checkout <branch_name>
Switch to a branch.

git branch -D <branch_name>
Delete a branch (e.g., git branch -D featured).

git merge <branch_name> -m "message"
Merge a branch into the current branch.

Remote Repositories (GitHub Integration)
git remote add <remote_name> <url>
Link a local repo to a remote (e.g., git remote add origin <URL>).

git remote
List linked remotes.

git remote -v
List remotes with URLs.

git remote remove <remote_name>
Remove a remote link (e.g., git remote remove origin).

git push <remote_name> <branch>
Upload a branch to a remote (e.g., git push origin main).

git push <remote_name> <branch> --set-upstream
Set upstream for future pushes.

git push <remote_name> <branch> -f
Force-push to overwrite remote.

git clone <url>
Clone a remote repository (e.g., git clone https://github.com/...).

git clone <url> <folder_name>
Clone into a specific folder.

git fetch
Update remote tracking branches.

git pull <remote_name> <branch>
Fetch and merge changes (e.g., git pull origin main).

Miscellaneous
rm -rf .git
Delete Git tracking from a project (⚠️ Caution: Irreversible!).

.gitignore
A file to specify untracked files/folders (not a command, but critical for Git).

Conflict Resolution
After resolving conflicts:

git add .
git commit -m "message"
Workflow Example
Feature Branch Workflow:

git branch new-feature
git checkout new-feature
git push origin new-feature

git checkout main
git pull origin main

git clone git@github-hameed008:username/repo.git
git@github-hameed009:username/repo.git
git clone git@github-hameed008:username/repo.git
ssh -T git@github-hameed008
git remote set-url origin git@github-hameed008:username/repo.git
url = git@hameed009.github.com:hameed008/computer-networking.git
url = git@github-hameed009:hameed008/computer-networking.git
git remote set-url origin git@github-hameed009:hameed009/computer-networking.git
git remote -v
origin git@github-hameed009:hameed009/computer-networking.git (fetch)
origin git@github-hameed009:hameed009/computer-networking.git (push)

git fetch origin

git config --global user.name "Hameed008"
git config --global user.email "hameed008@example.com"

# Or set it per repository

git config user.name "Hameed009"
git config user.email "hameed009@example.com"

git config --global url."git@github-hameed009:".insteadOf "git@github.com:hameed009/"

git push -u origin main
git branch -M main
git config --list

git config --get user.name
git config --get user.email

git config --global --get user.name
git config --global --get user.email

git config --global --unset user.name
git config --global --unset user.email

git config --unset user.name
git config --unset user.email

git push origin main
git push -u origin main
git pull origin main

git push origin feature-1
git push -u origin feature-1

git push
git pull

git push origin --delete master

git init --initial-branch=main

git config --global init.defaultBranch
git config --global init.defaultBranch main
git branch

git config --local --list
git config --global --list
git commit --amend --reset-author
git rebase -i --root --exec 'git commit --amend --reset-author --no-edit'
git log --format='%H %an <%ae>'
git config --show-origin --list
git log -1
git submodule add ../sub-repo
git config --global protocol.file.allow always

git remote -v
git remote show
git remote get-url orgin  
git remote show origin
git config --get remote.origin.url

==========================================================

git init
git init --initial-branch=main

git clone <repository-url>
git clone <url> <folder>
git status

git add <file\|folder>
git add .

git commit --amend
git commit -m "Commit message"
git commit --amend --reset-author

git log

git branch
git branch <branch-name>
git checkout <branch-name>
git checkout <commit-hash>
git checkout -b <branch>
git checkout -- <file>
git checkout <branch> <file>

git branch -r
git branch -d <branch-name>
git branch -D <branch>

git switch <branch-name>

git merge
git merge <branch-name>

git push
git push <remote> <branch>
git push -u <remote> <branch>
git push -u origin new-feature
git push -f
git push --force

git fetch
git pull
git pull <remote> <branch>

git remote
git remote add origin <repository-url>
git remote set-url origin <url>

git remote -v
git remote remove <name>
git remote show
git remote get-url orgin  
git remote show origin
git config --get remote.origin.url

git stash

git reset
git reset <file>
git reset --hard <commit-hash>

git revert
git revert <commit-hash>

git diff
git stats

git rm
git rm --cached <file>

rm -rf .git

git config
git config user.name "Name"
git config user.email "email"  
git config --global user.name "Name"
git config --global user.email "email"

git config --global --get user.name`  
git config --global --unset user.name`

git config --local --list
git config --list

git config --show-origin --list

git config --global alias.<shortcut> <command>
git config --global url."<new-url>".insteadOf "<old-url>"

git log --all --graph

git rebase
git rebase -i

git submodule add <url>
git reflog
git add . + git commit

File/Command

.gitignore

git restore
git tag
git cherry-pick
git bisect
git mv
git help
git <command> --help.
