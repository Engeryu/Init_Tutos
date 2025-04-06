# 🧰 Git & GitHub Initialization Guide

## ⚙️ Prerequisites

### 🐧 Linux (If you are on Windows but want to use WSL, check this [README.md]() beforehand) :

- `sudo apt update && sudo apt upgrade`
- `sudo apt install git gh curl tree`

### 🪟 Windows (Requires a Microsoft connected account) :

* `winget install GitHub.cli Git.Git`

---

## 🔧 Configure Git environment in your system:

### 🛠️ Git and GitHub-CLI configuration:

* Configure your Git [username](https://docs.github.com/en/get-started/git-basics/setting-your-username-in-git) and [email](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-personal-account-on-github/managing-email-preferences/setting-your-commit-email-address):

  * `git config --global user.name "Your_Github_Username"`
  * `git config --global user.email "your_github_email@example.com"`
* Open [Personal Access Tokens (Classic)](https://github.com/settings/tokens), click on "Generate new token", and choose the classic option. Then:

  * Enter a name in the `note` field, e.g., "CLI Management"
  * Select (at least): `repo`, `admin:public_key`, `user`, `delete_repo`, `admin:ssh_signing_key`
  * Click on "Generate token"
  * Copy and save the token somewhere secure (a secure note or encrypted storage is recommended, but plain Notepad can work too)
* Next, add your new token to `gh`:

  * `gh auth login`
  * Press Enter on the highlighted "GitHub.com"
  * Highlight "Skip" and press Enter
  * Highlight `Paste an authentication token` and press Enter

### 🔐 GitHub SSH configuration:

Your token is now linked to your local machine! Now, check if any SSH keys already exist (`id_rsa.pub`, `id_ecdsa.pub`, or `id_ed`):

* `ls ~/.ssh`
* If none exist, generate a new one:

  * `ssh-keygen -t ed25519 -C "your_github_email@example.com"`
* Your SSH key will be created. You'll see some prompts. Simply press Enter at each one:

  ```bash
  Generating public/private ed25519 key pair.
  Enter file in which to save the key (C:\Users\yourname/.ssh/id_ed25519): [Press Enter]
  Enter passphrase (empty for no passphrase): [Press Enter]
  Enter same passphrase again: [Press Enter]
  ```
* You should see:

  ```bash
  Your identification has been saved in C:\Users\yourname/.ssh/id_ed25519
  Your public key has been saved in C:\Users\yourname/.ssh/id_ed25519.pub
  The key fingerprint is:
  SHA256:RandomAlphaNumericKey your_github_email@example.com
  The key's randomart image is:
  +---[ED25519 256]---+
  |       o=.         |
  |    o  o++E         |
  |   + . Ooo.         |
  |    + O B..         |
  |     = *S.          |
  |      o             |
  |                    |
  |                    |
  |                    |
  +-------[SHA256]-----+
  ```
* Now add your SSH key to GitHub:

  * `gh ssh-key add ~/.ssh/id_ed25519.pub --title key_name`
    (To add a title to your SSH key, you can also write -t instead of --title)
* You can access your SSH key anytime by checking:
* `gh ssh-key list` (SSH keys stored in GitHub)
  or
* `cat ~/.ssh/id_ed25519.pub` (SSH key stored in your local machine)

---

### ✅ All Set!

Well done! Your local and remote environments are now fully connected and compatible.
You can read [🛠️ GitHub CLI Repository Initialization](./02-Github_Repo_Init.md) to learn how to list, create, and delete a repository!

**📚 PS:** If you want to deepen your knowledge of Git and GitHub configuration, here are the links to the [Git Documentation](https://git-scm.com/docs), the [GitHub-CLI Documentation](https://cli.github.com/manual/), and the [GitHub Documentation](https://docs.github.com/en).

🚀 Feel free to check other [guides](../README.md) to learn more technos!
