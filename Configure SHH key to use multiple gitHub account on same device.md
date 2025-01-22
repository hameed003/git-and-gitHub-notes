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

![Command To Generate A SSH Key](https://assets.digitalocean.com/articles/alligator/boo.svg "Command to generate a ssh key")

### Rename ssh key file name

![Command To Generate A SSH Key](https://assets.digitalocean.com/articles/alligator/boo.svg "Command to generate a ssh key")

### View ssh key method 1

![Command To Generate A SSH Key](https://assets.digitalocean.com/articles/alligator/boo.svg "Command to generate a ssh key")

### View ssh key method 2

![Command To Generate A SSH Key](https://assets.digitalocean.com/articles/alligator/boo.svg "Command to generate a ssh key")

### Copy ssh key

![Command To Generate A SSH Key](https://assets.digitalocean.com/articles/alligator/boo.svg "Command to generate a ssh key")

## 2. Add SSH Keys to the Agent

Start the SSH agent and add your keys:

```
eval "$(ssh-agent -s)"
```

### Start ssh agent

![Command To Generate A SSH Key](https://assets.digitalocean.com/articles/alligator/boo.svg "Command to generate a ssh key")

```
ssh-add ~/.ssh/id_hameed008
```

### Add ssh agent

![Command To Generate A SSH Key](https://assets.digitalocean.com/articles/alligator/boo.svg "Command to generate a ssh key")

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

### Generate ssh key

![Clone repo from gitHub image 1](https://assets.digitalocean.com/articles/alligator/boo.svg "Command to generate a ssh key")

### Generate ssh key

![Clone repo from gitHub image 2](https://assets.digitalocean.com/articles/alligator/boo.svg "Command to generate a ssh key")

### Generate ssh key

![Clone repo from gitHub image 3](https://assets.digitalocean.com/articles/alligator/boo.svg "Command to generate a ssh key")

## 6. Push An Existing Repo To GitHub

### Generate ssh key

![Push Existing repo to gitHub image 1](https://assets.digitalocean.com/articles/alligator/boo.svg "Command to generate a ssh key")

![Push Existing repo to gitHub image 2](https://assets.digitalocean.com/articles/alligator/boo.svg "Command to generate a ssh key")

![Push Existing repo to gitHub image 3](https://assets.digitalocean.com/articles/alligator/boo.svg "Command to generate a ssh key")

![Push Existing repo to gitHub image 4](https://assets.digitalocean.com/articles/alligator/boo.svg "Command to generate a ssh key")
