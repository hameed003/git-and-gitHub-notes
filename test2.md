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
