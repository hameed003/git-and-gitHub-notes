1. `git config --global core.editor emacs` or `git config --global core.editor vim`

# Configuring Git's Default Editor

These commands configure the default text editor used by Git for actions like writing commit messages, rebasing, or resolving merge conflicts.

## 1. Setting the Editor Globally

### Emacs

Set Emacs as the default editor for Git globally (applies to all repositories on your system):

```bash
git config --global core.editor emacs
```

Now, when you run `git commit`, Git will open Emacs for you to write the commit message.

### Vim

Set Vim as the default editor for Git globally:

```bash
git config --global core.editor vim
```

If you run this after setting Emacs, Vim will override Emacs as the default editor.

## 2. Key Notes

### `--global` Flag:

- Applies the setting to your user account (stored in `~/.gitconfig`).
- Remove `--global` to set the editor for a single repository (stored in `.git/config`).

### Supported Editors:

Replace `emacs` or `vim` with any editor installed on your system (e.g., `nano`, `code`, `subl`).

#### Example for VS Code:

```bash
git config --global core.editor "code --wait"
```

### Verify the Setting:

```bash
git config --global core.editor  # Output: vim (or your configured editor)
```

### Editor Requirements:

- The editor must be installed and accessible in your system’s `PATH`.
- For GUI editors (e.g., VS Code), include flags like `--wait` to keep Git waiting until you close the editor.

## 3. Why Configure This?

### Commit Messages:

Git opens your editor to write commit messages.

### Rebase/Merge Conflicts:

Editors are used during interactive rebase (`git rebase -i`) or conflict resolution.

## 4. Reset to Default

To unset the editor and use Git’s default (usually `vi`):

```bash
git config --global --unset core.editor
```

## 5. Example Workflow

### Configure Vim as Your Editor:

```bash
git config --global core.editor vim
```

### Create a Commit:

```bash
git commit  # Opens Vim to write the commit message
```

Save and exit Vim (`:wq`) to finalize the commit.

## 6. Common Issues

### Editor Not Found:

If the editor isn’t installed, Git will throw an error:

```
error: cannot run emacs: No such file or directory
```

### Incorrect Syntax:

Use quotes for editors with spaces or flags:

```bash
git config --global core.editor "atom --wait"

























The command git config --global core.editor emacs on Linux sets your global Git editor to Emacs,

meaning whenever Git needs to open a text editor for editing commit messages or other prompts, it will launch Emacs by default.
```
