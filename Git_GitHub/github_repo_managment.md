# 🛠️ GitHub CLI Repository Management

## 📁 Repository Prerequisite:
If you didn't set up your Git and GitHub environment locally, read [README.md]()!
If you don't have any repository on GitHub, read [README.md]()!
If you don't have any repository on your local machine but want to interact with an existing one, then:
* `git clone git@github:Username/repository_name.git`

---

## 🔁 Repository Sync:
With Git, four main commands are frequently used (in this order):
* To fetch all files and content from the repository to your local machine and stay synchronized:
  * `git pull`
* To add files to Git tracking (ready to be sent):
  * `git add your_content` or `git add .`  
    (The first option requires specifying one or more files/folders. The second means you want to stage everything, including hidden files, while respecting `.gitignore`.)  
    ⚠️ Never use `git add *`, as it acts like `git add .` but does **not** respect `.gitignore`.
* To add a comment to your new checkpoint (useful to revert changes later):
  * `git commit -m "Your comment"`  
    (You can commit without a message, but it’s much harder to track changes this way.)
* To send your committed files to your repository:
  * `git push` or `git push -u origin branch_name`  
    (The first is enough if you're working only on `main`; otherwise, use the second for multiple branches.)

---

## 🧩 Repository Miscellaneous:
There’s a fifth command you’ll use often, at any point:
* `git status`
And a sixth one, useful to temporarily hide uncommitted changes:
* `git stash`
* `git stash pop`

---

## 🗑️ Delete Repository and Local Contents
To use to delete content from both your repository **and** your local machine:

* `git rm -r your_content`
* `git commit -m "Your comment"`
* `git push origin main`

---

## 🚫 Delete Repository Contents ONLY
To use **without affecting** your local machine:

* `git rm -r --cached your_content`
* `git commit -m "Your comment"`
* `git push origin main`

---

## ❌ Delete Repository from GitHub ONLY
* `gh repo delete repository_name`
You’ll be prompted to confirm the deletion—follow the instructions, then press Enter:
```bash
? Type Username/repository_name to confirm deletion: Username/repository_name [Press Enter]
```

---

✅ Congratulations! You now know the essential commands to efficiently use GitHub from your terminal! 🎉