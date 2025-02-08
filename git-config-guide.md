# Git Configuration Commands Guide

A comprehensive list of Git commands for configuring your environment, user settings, aliases, and more.

---

## 1. User Identity Configuration

### Set Global User Name & Email

```sh
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

**Explanation:** Sets your name and email for all repositories on your machine.

**Example:**

```sh
git config --global user.name "John Doe"
git config --global user.email "john.doe@company.com"
```

### Set Repository-Specific User Name & Email

```sh
git config user.name "Project Name"
git config user.email "project.email@example.com"
```

**Explanation:** Overrides global settings for a specific repository.

**Example:**

```sh
cd my-project/
git config user.name "MyProject Bot"
git config user.email "bot@myproject.com"
```

## 2. Aliases (Shortcuts)

### Create a Global Alias

```sh
git config --global alias.<shortcut> "<command>"
```

**Explanation:** Shortens frequently used commands.

**Examples:**

```sh
git config --global alias.s "status"          # `git s` for status
git config --global alias.l "log --oneline"   # `git l` for compact log
git config --global alias.co "checkout"       # `git co` for checkout
```

### Create a Local Alias

```sh
git config alias.<shortcut> "<command>"
```

**Explanation:** Defines aliases for the current repository only.

**Example:**

```sh
git config alias.rh "reset --hard HEAD"  # `git rh` to reset changes
```

## 3. Default Branch Configuration

### Set Default Branch Name Globally

```sh
git config --global init.defaultBranch main
```

**Explanation:** Changes the default branch name from master to main for new repositories.

### Initialize a Repository with a Specific Branch

```sh
git init --initial-branch=main
```

**Example:**

```sh
mkdir new-project && cd new-project
git init --initial-branch=main
```

## 4. Viewing Configurations

### List All Configurations

```sh
git config --list
```

### List Global Configurations

```sh
git config --global --list
```

### List Local Configurations

```sh
git config --local --list
```

### Check Where a Setting is Defined

```sh
git config --show-origin --get <key>
```

**Example:**

```sh
git config --show-origin --get user.name
# Output: file:/home/user/.gitconfig  john.doe
```

## 5. Unsetting Configurations

### Remove a Global Setting

```sh
git config --global --unset <key>
```

**Example:**

```sh
git config --global --unset user.email
```

### Remove a Local Setting

```sh
git config --local --unset <key>
```

**Example:**

```sh
git config --local --unset alias.rh
```

## 6. URL Rewriting (SSH/HTTPS)

### Replace HTTPS with SSH Globally

```sh
git config --global url."git@github.com:".insteadOf "https://github.com/"
```

**Example:**

```sh
git clone https://github.com/user/repo.git  # Clones via SSH instead
```

### Custom SSH Host Configuration

```sh
git config --global url."git@custom-host:".insteadOf "https://custom-domain.com/"
```

**Example:**

```sh
git clone https://custom-domain.com/user/repo.git  # Uses `git@custom-host:user/repo.git`
```

## 7. Text Editor Configuration

### Set Default Commit Editor

```sh
git config --global core.editor "editor-name"
```

**Examples:**

```sh
git config --global core.editor "nano"      # Use Nano
git config --global core.editor "code --wait"  # Use VS Code
```

## 8. SSH & Protocol Settings

### Allow File Protocol for Submodules

```sh
git config --global protocol.file.allow always
```

**Explanation:** Permits cloning submodules via file:// URLs.

## 9. Ignoring Files (Global .gitignore)

### Configure a Global Gitignore File

```sh
git config --global core.excludesFile ~/.gitignore_global
```

### Create the file:

```sh
touch ~/.gitignore_global
```

### Add patterns to ignore (e.g., .DS_Store, \*.log).

## 10. Submodule Configuration

### Allow Submodule Recursive Clones

```sh
git config --global submodule.recurse true
```

**Explanation:** Automatically initializes and clones submodules when running git clone.

## 11. Credential Management

### Cache Credentials for HTTPS

```sh
git config --global credential.helper "cache --timeout=3600"
```

**Explanation:** Stores HTTPS credentials in memory for 1 hour (3600 seconds).

### Store Credentials on Disk

```sh
git config --global credential.helper "store"
```

⚠️ **Warning:** Saves credentials in plain text at `~/.git-credentials`.

## 12. Troubleshooting Configuration

### Check Effective Configuration

```sh
git config --show-origin --list
```

**Explanation:** Shows where each setting is defined (global, local, or system).

### Reset Configuration to Defaults

```sh
git config --global --unset-all <key>
```

**Example:**

```sh
git config --global --unset-all core.editor  # Remove editor setting
```

## Example Workflow: Configure a New Machine

### Set Global Identity:

```sh
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

### Create Aliases:

```sh
git config --global alias.s "status"
git config --global alias.l "log --oneline --graph --all"
```

### Set Default Branch:

```sh
git config --global init.defaultBranch main
```

### Configure SSH URLs:

```sh
git config --global url."git@github.com:".insteadOf "https://github.com/"
```
