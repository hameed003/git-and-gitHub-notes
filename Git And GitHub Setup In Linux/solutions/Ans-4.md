The error `'gh' is not recognized as an internal or external command` indicates that the **GitHub CLI (`gh`)** is not installed on your system, or it is not added to your system's **PATH**. Let’s fix this step by step.

---

### **Step 1: Install GitHub CLI (`gh`)**

The GitHub CLI is a powerful tool for interacting with GitHub from the command line. To install it:

1. **Download the Installer**:

   - Go to the official GitHub CLI website: [GitHub CLI](https://cli.github.com/).
   - Download the installer for Windows.

2. **Run the Installer**:

   - Open the downloaded `.msi` file.
   - Follow the installation wizard to install the GitHub CLI.

3. **Verify Installation**:
   - Open a new Command Prompt or PowerShell window.
   - Run:
     ```bash
     gh --version
     ```
   - If the installation was successful, this will display the installed version of `gh`.

---

### **Step 2: Add GitHub CLI to PATH (if needed)**

If the `gh` command is still not recognized after installation, it might not be added to your system's **PATH**. Here’s how to fix it:

1. **Find the Installation Directory**:

   - By default, the GitHub CLI is installed in:
     ```
     C:\Program Files\GitHub CLI\
     ```
   - Look for the `gh.exe` file in this directory.

2. **Add to PATH**:

   - Press `Win + S` and search for **Environment Variables**.
   - Click **Edit the system environment variables**.
   - In the **System Properties** window, click **Environment Variables**.
   - Under **System variables**, find the `Path` variable and click **Edit**.
   - Click **New** and add the path to the GitHub CLI installation directory (e.g., `C:\Program Files\GitHub CLI\`).
   - Click **OK** to save the changes.

3. **Verify PATH Update**:
   - Open a new Command Prompt or PowerShell window.
   - Run:
     ```bash
     gh --version
     ```
   - If the PATH was updated correctly, this will display the installed version of `gh`.

---

### **Step 3: Authenticate with GitHub CLI**

Once the GitHub CLI is installed and working, you can authenticate it with your GitHub account.

1. **Run the Login Command**:

   ```bash
   gh auth login
   ```

2. **Follow the Prompts**:

   - Choose `GitHub.com` as the host.
   - Select `HTTPS` or `SSH` for authentication (recommended: `HTTPS` for simplicity).
   - If you choose `HTTPS`, authenticate with a **personal access token (PAT)**:
     - Go to [GitHub Settings > Developer settings > Personal access tokens](https://github.com/settings/tokens).
     - Generate a new token with the `repo` scope.
     - Paste the token when prompted.

3. **Check Authentication Status**:
   After logging in, verify your authentication status:
   ```bash
   gh auth status
   ```
   This will display information about your authenticated account and the authentication method (e.g., `oauth_token` or `ssh`).

---

### **Step 4: Use GitHub CLI**

Now that `gh` is installed and authenticated, you can use it to interact with GitHub. Here are some common commands:

- **View Your Repositories**:

  ```bash
  gh repo list
  ```

- **Create a New Repository**:

  ```bash
  gh repo create
  ```

- **Clone a Repository**:

  ```bash
  gh repo clone owner/repo
  ```

- **Create a Pull Request**:

  ```bash
  gh pr create
  ```

- **Check Your GitHub Status**:
  ```bash
  gh auth status
  ```

---

### **Troubleshooting**

If you still encounter issues:

1. **Restart Your Terminal**:

   - Close and reopen Command Prompt or PowerShell after installing `gh` or updating the PATH.

2. **Reinstall GitHub CLI**:

   - Uninstall the GitHub CLI from **Add or Remove Programs** and reinstall it.

3. **Check for Conflicting Software**:
   - Ensure there are no conflicting versions of `gh` or other CLI tools.

---

Let me know if you need further assistance!

# Doubt:

since you said that `gitHub CLI` is not installed in my system then how i am able to use `git` and `gitHub`. [Ans-5](https://github.com/hameed003/git-and-gitHub-notes/blob/main/Git%20And%20GitHub%20Setup%20In%20Linux/solutions/Ans-5.md)
