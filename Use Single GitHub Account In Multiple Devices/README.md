# Way to use GitHub on multiple machines with SSH

Let’s break this down step by step! I’ll show you the most secure and scalable way to use GitHub on multiple machines with SSH, so you can switch between them seamlessly.

Here’s how to do it the **right way**:

---

## 🔑 **Step 1: Generate SSH Keys on Each Machine**

1. **On Machine A (e.g., your laptop):**

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

Press **Enter** to save the key in the default location (`~/.ssh/id_ed25519`).  
Leave the passphrase empty (or set one for extra security).

Then view your public key:

```bash
cat ~/.ssh/id_ed25519.pub
```

Copy the entire output.

2. **On Machine B (e.g., your desktop):**
   Repeat the same steps:

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

View the public key:

```bash
cat ~/.ssh/id_ed25519.pub
```

---

## 🛜 **Step 2: Add SSH Keys to GitHub**

1. **Log in to GitHub → Settings → SSH and GPG Keys → New SSH Key**

2. **Add the key from Machine A:**

- Title: **Laptop (or whatever makes sense)**
- Paste the public key

3. **Add the key from Machine B:**

- Title: **Desktop**
- Paste the public key

---

## 🚀 **Step 3: Configure SSH on Each Machine**

1. **On Machine A:**  
   Tell your SSH client to use the correct private key:

```bash
nano ~/.ssh/config
```

Add this:

```
# GitHub from Laptop
Host github-laptop
    HostName github.com
    User git
    IdentityFile ~/.ssh/id_ed25519
```

2. **On Machine B:**  
   Do the same, but change the **host name**:

```
# GitHub from Desktop
Host github-desktop
    HostName github.com
    User git
    IdentityFile ~/.ssh/id_ed25519
```

Save the file.

---

## ✅ **Step 4: Test the Connection**

1. **On Machine A:**

```bash
ssh -T github-laptop
```

2. **On Machine B:**

```bash
ssh -T github-desktop
```

If everything is set up correctly, you’ll see this message:

```
Hi <username>! You’ve successfully authenticated...
```

---

## 🔗 **Step 5: Clone and Push Repositories**

1. **On Machine A (laptop):**

```bash
git clone git@github-laptop:username/repository.git
```

2. **On Machine B (desktop):**

```bash
git clone git@github-desktop:username/repository.git
```

Now you can work on your project from both machines, commit your changes, and push them:

```bash
git add .
git commit -m "Update from laptop"
git push
```

---

## 🚩 **Why This Setup is Secure and Scalable**

- **Separate Keys for Each Machine:** If one device is lost or compromised, you only need to remove that device’s key from GitHub.
- **Clear Device Identification:** You can see which device made a commit or push.
- **No Need to Manually Switch Keys:** The SSH config handles the correct key selection for you.

Would you like me to show you how to set an upstream branch or how commits appear on GitHub with these keys? Let me know — I’d love to help! 🚀
