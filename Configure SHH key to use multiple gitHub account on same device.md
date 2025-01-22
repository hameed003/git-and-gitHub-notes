# Configure SHH Key To Use Multiple GitHub Account On Same Device.

## 1. Create SSH Keys

Generate separate SSH keys for each GitHub account if you haven't already:

```
ssh-keygen -t ed25519
```

OR

```
ssh-keygen -t ed25519 -C "your_email@example.com"
```

Save each key with a unique name, such as ~/.ssh/id_hameed008 and ~/.ssh/id_hameed003.

## Practical Demonstration:

### Generate ssh key

![Command To Generate A SSH Key](https://github.com/hameed003/git-and-gitHub-notes/blob/main/images/ssh%20setup%20images/01%20generate%20ssh%20key.png "Command to generate a ssh key")

### Rename ssh key file name

![Command To Generate A SSH Key](https://github.com/hameed003/git-and-gitHub-notes/blob/main/images/ssh%20setup%20images/02%20rename%20ssh%20key%20file%20name.png "Command to generate a ssh key")

### View ssh key method 1

![View ssh key method 1](https://github.com/hameed003/git-and-gitHub-notes/blob/main/images/ssh%20setup%20images/03%20view%20ssh%20key%201.png "View ssh key method 1")

### View ssh key method 2

![View ssh key method 2](https://github.com/hameed003/git-and-gitHub-notes/blob/main/images/ssh%20setup%20images/04%20view%20ssh%20key%202.png "View ssh key method 2")

### Copy ssh key

![Copy ssh key](https://github.com/hameed003/git-and-gitHub-notes/blob/main/images/ssh%20setup%20images/05%20copy%20ssh%20key.png "Copy ssh key")

## 2. Add SSH Keys to the Agent

Start the SSH agent and add your keys:

```
eval "$(ssh-agent -s)"
```

### Start ssh agent

![Start ssh agent](https://github.com/hameed003/git-and-gitHub-notes/blob/main/images/ssh%20setup%20images/06%20start%20ssh%20agent.png "Start ssh agent")

```
ssh-add ~/.ssh/id_hameed008
```

### Add ssh agent

![Add ssh agent](https://github.com/hameed003/git-and-gitHub-notes/blob/main/images/ssh%20setup%20images/07%20add%20ssh%20agent.png "Add ssh agent")

### Setup ssh key final image 1

![Setup ssh key final image 1](https://github.com/hameed003/git-and-gitHub-notes/blob/main/images/ssh%20setup%20images/08%20setup%20ssh%20key%20final%20image%201.png "Setup ssh key final image 1")

### Setup ssh key final image 2

![Setup ssh key final image 2](https://github.com/hameed003/git-and-gitHub-notes/blob/main/images/ssh%20setup%20images/09%20setup%20ssh%20key%20final%20image%202.png "Setup ssh key final image 2")

### **_Repeate the above procedure for as many `gitHub` account as you want to use on your machine._**

## 3. Configure SSH in ~/.ssh/config

Edit or create the SSH config file:

```
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
git remote set-url origin git@github-hameed008:username/repo.git
```

## 5.Clone A Repository From GitHub

### Clone repo from gitHub image 1

![Clone repo from gitHub image 1](https://github.com/hameed003/git-and-gitHub-notes/blob/main/images/ssh%20setup%20images/10%20clone%20repo%20from%20gitHub%20image%201.png "Clone repo from gitHub image 1")

### Clone repo from gitHub image 2

![Clone repo from gitHub image 2](https://github.com/hameed003/git-and-gitHub-notes/blob/main/images/ssh%20setup%20images/11%20clone%20repo%20from%20gitHub%20image%202.png "Clone repo from gitHub image 2")

### Generate ssh key

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
