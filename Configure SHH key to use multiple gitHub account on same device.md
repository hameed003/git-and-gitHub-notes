# Configure SHH Key To Use Multiple GitHub Account On Same Device.

## Practical Demonstration:

## 1. Generate SSH Keys

Generate separate SSH keys for each GitHub account if you haven't already:

```bash
ssh-keygen -t ed25519
```

OR

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

Save each key with a unique name, such as `~/.ssh/id_hameed008` and `~/.ssh/id_hameed003`.

### Generate ssh key

![Command To Generate A SSH Key](https://github.com/hameed003/git-and-gitHub-notes/blob/main/images/ssh%20setup%20images/01%20generate%20ssh%20key.png "Command to generate a ssh key")

### Rename ssh key file name

![Rename ssh key file name](https://github.com/hameed003/git-and-gitHub-notes/blob/main/images/ssh%20setup%20images/02%20rename%20ssh%20key%20file%20name.png "Rename ssh key file name")

### Command 1 to view ssh public key

```bash
 cat ~/.ssh/id_hameed009.pub
```

![Command 1 to view ssh public key](https://github.com/hameed003/git-and-gitHub-notes/blob/main/images/ssh%20setup%20images/03%20view%20ssh%20key%201.png "Command 1 to view ssh public key")

### Command 2 to view ssh public key

```bash
tail <~/.ssh/id_hameed009.pub
```

![Command 2 to view ssh public key](https://github.com/hameed003/git-and-gitHub-notes/blob/main/images/ssh%20setup%20images/04%20view%20ssh%20key%202.png "Command 2 to view ssh public key")

### Command to copy ssh public key

```bash
clip <~/.ssh/id_hameed009.pub
```

![ Command to copy ssh public key](https://github.com/hameed003/git-and-gitHub-notes/blob/main/images/ssh%20setup%20images/05%20copy%20ssh%20key.png " Command to copy ssh public key")

Now paste this `ssh public key` to the `SSH and GPS keys` section in gitHub Settings.

## 2. Add SSH Keys to the Agent

Start the SSH agent and add your keys:

### Command to start ssh agent

```bash
eval "$(ssh-agent -s)"
```

![Command to start ssh agent](https://github.com/hameed003/git-and-gitHub-notes/blob/main/images/ssh%20setup%20images/06%20start%20ssh%20agent.png "Command to start ssh agent")

### Command to add ssh agent

```bash
ssh-add ~/.ssh/id_hameed008
```

![Command to add ssh agent](https://github.com/hameed003/git-and-gitHub-notes/blob/main/images/ssh%20setup%20images/07%20add%20ssh%20agent.png "Command to add ssh agent")

### Setup ssh key final image 1

![Setup ssh key final image 1](https://github.com/hameed003/git-and-gitHub-notes/blob/main/images/ssh%20setup%20images/08%20setup%20ssh%20key%20final%20image%201.png "Setup ssh key final image 1")

### Setup ssh key final image 2

![Setup ssh key final image 2](https://github.com/hameed003/git-and-gitHub-notes/blob/main/images/ssh%20setup%20images/09%20setup%20ssh%20key%20final%20image%202.png "Setup ssh key final image 2")

### **_Repeate the above procedure for as many `gitHub` account as you want to use on your machine._**

## 3. Configure SSH in ~/.ssh/config

Edit or create the SSH config file:

```bash
nano ~/.ssh/config
```

Add the following entries to the config file:

```bash
# hameed008 account
Host github-hameed008
HostName github.com
User git
PreferredAuthentications publickey
IdentityFile ~/.ssh/id_hameed008

# hameed003 account
Host github-hameed003
HostName github.com
User git
PreferredAuthentications publickey
IdentityFile ~/.ssh/id_hameed003
```

Save the file ( `Ctrl+O`, then `Ctrl+X` in nano ).

## 4. Update Repository Remote URLs

For repositories linked to each account, update the remote URLs to use the corresponding alias:

For hameed008:

```
git remote set-url origin git@github-hameed003:hameed003/repo.git
```

## **_Things to remember while cloning a repo from the gitHub or adding a repo from the gitHub to push an existing repo to gitHub:_**

Replace `.com` from the `remote url` with gitHub username which is`-hameed003` in this case while cloning a repo or adding a repo from gitHub with `ssh url` like below.

original url

```bash
 git remote add origin git@github.com:hameed003/test.git
```

modified url

```bash
git remote add origin git@github.hameed003:hameed003/test.git
```

**Note-** If you do not replace `.com` from the `remote url` with gitHub username which is`-hameed003` in this case and cloned the repo, so when we try to push the repo to `gitHub` we will get the following error.

![Error while pushing a reop to gitHub](https://github.com/hameed003/git-and-gitHub-notes/blob/main/images/ssh%20setup%20images/10%20Error%20while%20pushing%20a%20reop%20to%20gitHub.png "Error while pushing a reop to gitHub")

To resolve this now we have to set the modified `remote url` explicitly like below.

![Setting remote url explicitly](https://github.com/hameed003/git-and-gitHub-notes/blob/main/images/ssh%20setup%20images/11%20Setting%20remote%20url%20explicitly.png "Setting remote url explicitly")

```bash
git remote set-url origin git@github-hameed003:username/repoName.git
```

## 5.Clone A Repository From GitHub

### Clone repo from gitHub image 1

![Clone repo from gitHub image 1](https://github.com/hameed003/git-and-gitHub-notes/blob/main/images/ssh%20setup%20images/10%20clone%20repo%20from%20gitHub%20image%201.png "Clone repo from gitHub image 1")

### Clone repo from gitHub image 2

![Clone repo from gitHub image 2](https://github.com/hameed003/git-and-gitHub-notes/blob/main/images/ssh%20setup%20images/11%20clone%20repo%20from%20gitHub%20image%202.png "Clone repo from gitHub image 2")

### Clone repo from gitHub image 3

![Clone repo from gitHub image 3](https://github.com/hameed003/git-and-gitHub-notes/blob/main/images/ssh%20setup%20images/12%20clone%20repo%20from%20gitHub%20image%203.png "Clone repo from gitHub image 13")

## 6. Push An Existing Repo To GitHub

### Push Existing repo to gitHub image 1

![Push Existing repo to gitHub image 1](https://github.com/hameed003/git-and-gitHub-notes/blob/main/images/ssh%20setup%20images/13%20push%20existing%20repo%20to%20gitHub%20image%201.png "Push Existing repo to gitHub image 1")

### Push Existing repo to gitHub image 2

![Push Existing repo to gitHub image 2](https://github.com/hameed003/git-and-gitHub-notes/blob/main/images/ssh%20setup%20images/14%20push%20existing%20repo%20to%20gitHub%20image%202.png "Push Existing repo to gitHub image 2")

### Push Existing repo to gitHub image 3

![Push Existing repo to gitHub image 3](https://github.com/hameed003/git-and-gitHub-notes/blob/main/images/ssh%20setup%20images/15%20push%20existing%20repo%20to%20gitHub%20image%203.png "Push Existing repo to gitHub image 3")

### Push Existing repo to gitHub image 4

![Push Existing repo to gitHub image 4](https://github.com/hameed003/git-and-gitHub-notes/blob/main/images/ssh%20setup%20images/16%20push%20existing%20repo%20to%20gitHub%20image%204.png "Push Existing repo to gitHub image 4")
