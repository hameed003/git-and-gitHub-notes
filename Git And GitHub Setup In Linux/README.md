Using Git and GitHub on Linux involves several steps, including installing Git, configuring it, creating repositories, and interacting with GitHub. Below is a detailed guide with examples to help you get started.

### 1. **Install Git on Linux**

First, you need to install Git on your Linux system. You can do this using your package manager.

#### On Ubuntu/Debian:

```bash
sudo apt update
sudo apt install git
```

#### On Fedora:

```bash
sudo dnf install git
```

#### On CentOS/RHEL:

```bash
sudo yum install git
```

#### Verify Installation:

```bash
git --version
```

This should display the installed version of Git, confirming that the installation was successful.

### 2. **Configure Git**

After installing Git, you need to configure it with your username and email address. This information will be used in your commits.

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

You can check your configuration settings using:

```bash
git config --list
```

### 3. **Create a Local Git Repository**

To start using Git, you need to create a repository. You can either create a new repository or clone an existing one.

#### Initialize a New Repository:

Navigate to the directory where you want to create the repository and run:

```bash
mkdir my-project
cd my-project
git init
```

This initializes a new Git repository in the `my-project` directory.

#### Add Files to the Repository:

Create a new file or add existing files to the repository:

```bash
echo "# My Project" > README.md
git add README.md
```

#### Commit the Changes:

```bash
git commit -m "Initial commit"
```

### 4. **Connect to GitHub**

To connect your local repository to GitHub, you need to create a repository on GitHub and then link it to your local repository.

#### Create a New Repository on GitHub:

1. Go to [GitHub](https://github.com) and log in.
2. Click on the `+` sign in the top right corner and select "New repository".
3. Fill in the repository name, description, and choose whether it should be public or private.
4. Click "Create repository".

#### Link Local Repository to GitHub:

After creating the repository on GitHub, you will see a URL for your repository. Use this URL to link your local repository to GitHub.

```bash
git remote add origin https://github.com/your-username/your-repo-name.git
```

#### Push Local Repository to GitHub:

Push your local repository to GitHub:

```bash
git push -u origin master
```

The `-u` flag sets the upstream tracking reference, so future pushes can be done with just `git push`.

### 5. **Basic Git Commands**

Here are some basic Git commands you will frequently use:

#### Check Status:

```bash
git status
```

#### Add Changes:

```bash
git add <file-name>
```

or to add all changes:

```bash
git add .
```

#### Commit Changes:

```bash
git commit -m "Your commit message"
```

#### Push Changes to GitHub:

```bash
git push
```

#### Pull Changes from GitHub:

```bash
git pull
```

#### Clone a Repository:

To clone an existing repository from GitHub:

```bash
git clone https://github.com/your-username/your-repo-name.git
```

#### View Commit History:

```bash
git log
```

### 6. **Branching and Merging**

Git allows you to work on different branches, which is useful for developing new features or fixing bugs without affecting the main codebase.

#### Create a New Branch:

```bash
git branch new-feature
```

#### Switch to the New Branch:

```bash
git checkout new-feature
```

#### Merge Branches:

After completing work on a branch, you can merge it back into the main branch (usually `master` or `main`).

```bash
git checkout master
git merge new-feature
```

#### Delete a Branch:

```bash
git branch -d new-feature
```

### 7. **Handling Conflicts**

Sometimes, when merging branches or pulling changes, you may encounter conflicts. Git will mark the conflicts in the affected files, and you need to resolve them manually.

#### Resolve Conflicts:

1. Open the conflicted file and look for conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`).
2. Edit the file to resolve the conflict.
3. Add the resolved file:
   ```bash
   git add <file-name>
   ```
4. Commit the changes:
   ```bash
   git commit -m "Resolved merge conflict"
   ```

### 8. **Using .gitignore**

The `.gitignore` file is used to specify files and directories that Git should ignore. This is useful for excluding temporary files, build artifacts, or sensitive information.

#### Create a .gitignore File:

```bash
touch .gitignore
```

#### Add Patterns to .gitignore:

Edit the `.gitignore` file and add patterns for files or directories to ignore. For example:

```
# Ignore all .log files
*.log

# Ignore the build directory
/build
```

### 9. **Collaborating on GitHub**

GitHub allows multiple developers to collaborate on a project. Here are some common workflows:

#### Fork a Repository:

If you want to contribute to someone else's project, you can fork their repository. This creates a copy of the repository under your GitHub account.

1. Go to the repository on GitHub.
2. Click the "Fork" button in the top right corner.

#### Clone Your Fork:

```bash
git clone https://github.com/your-username/forked-repo-name.git
```

#### Add the Original Repository as a Remote:

```bash
git remote add upstream https://github.com/original-owner/original-repo-name.git
```

#### Sync Your Fork:

To keep your fork up-to-date with the original repository:

```bash
git fetch upstream
git checkout master
git merge upstream/master
```

#### Create a Pull Request:

After making changes and pushing them to your fork, you can create a pull request to propose your changes to the original repository.

1. Go to your fork on GitHub.
2. Click "New pull request".
3. Review the changes and click "Create pull request".

### 10. **Advanced Git Features**

#### Stashing Changes:

If you need to switch branches but don't want to commit your current changes, you can stash them:

```bash
git stash
```

To reapply the stashed changes:

```bash
git stash apply
```

#### Rebasing:

Rebasing is an alternative to merging that can create a cleaner commit history:

```bash
git checkout new-feature
git rebase master
```

#### Tagging:

Tags are used to mark specific points in the repository's history, often used for releases:

```bash
git tag v1.0.0
git push origin v1.0.0
```

### Conclusion

This guide covers the basics of using Git and GitHub on Linux. As you become more comfortable with these tools, you can explore more advanced features and workflows to enhance your development process. Git is a powerful tool, and mastering it will significantly improve your ability to manage and collaborate on software projects.

# Error:

when i use `https` method to clone or push a repo on gitHub i get this error: **`remote: Support for password authentication was removed on August 13, 2021.`**
why i get this error again and again and this is only in linux but not in windows [Ans-1](https://github.com/hameed003/git-and-gitHub-notes/blob/main/Git%20And%20GitHub%20Setup%20In%20Linux/solutions/Ans-1.md)
