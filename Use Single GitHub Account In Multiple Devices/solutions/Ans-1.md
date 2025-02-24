I’ll break it down step by step! Let’s say you want to use your GitHub account on multiple machines — like a laptop and a desktop — and you want to push/pull the same repositories across both.

Here’s how you can set it up:

---

### 🚀 **Step 1: Install Git**

Make sure Git is installed on both machines. You can check with:

```bash
git --version
```

If not installed:

- **Windows:** Download from [git-scm.com](https://git-scm.com/)
- **Linux (Ubuntu):**

```bash
sudo apt install git
```

---

### 🔑 **Step 2: Generate SSH Key (on each machine)**

You need SSH keys to authenticate with GitHub.

On **Machine A**, run:

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

Hit **Enter** to save the key. You’ll get:

```
~/.ssh/id_ed25519
```

Then, copy the key to your clipboard:

```bash
cat ~/.ssh/id_ed25519.pub
```

Do the **same process on Machine B**.

---

### 🛜 **Step 3: Add SSH Key to GitHub**

Go to **GitHub > Settings > SSH and GPG Keys > New SSH Key**.  
Add the copied public key.

Test the connection:

```bash
ssh -T git@github.com
```

If successful:

```
Hi <username>! You've successfully authenticated...
```

---

### 🏁 **Step 4: Clone Repository on Both Machines**

On **Machine A**:

```bash
git clone git@github.com:username/repo.git
cd repo
```

Make some changes:

```bash
echo "Hello from Machine A" > file.txt
git add file.txt
git commit -m "Add file from Machine A"
git push
```

On **Machine B**:

```bash
git clone git@github.com:username/repo.git
cd repo
```

Pull the latest changes:

```bash
git pull
```

---

### 📂 **Step 5: Push & Pull Across Machines**

Now, anytime you make changes on either machine:

1. **On Machine A (or B)**:

```bash
git add .
git commit -m "Your message"
git push
```

2. **On the other machine**:

```bash
git pull
```

This way, you can seamlessly switch between machines!

Would you like me to help you set up multiple GitHub accounts on a single machine or dive deeper into SSH key management? Let me know! 🚀

# Doubt:

Since we have generated `SSH` `public key` and ``private key` in both machine so which `public key` should I paste on GitHub. [Ans-2](https://github.com/hameed003/git-and-gitHub-notes/blob/main/Use%20Single%20GitHub%20Account%20In%20Multiple%20Devices/solutions/Ans-2.md)
