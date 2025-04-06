# 🛠️ GitHub CLI Repository Initialization

If you don't know what `gh` is or can't execute it, check [🧰Git &amp; GitHub Initialization Guide](./github_git_init.md)!

---

## 📁 Repository Listing (anywhere):

* `gh repo list`

---

## 🆕 Repository Creation (If you didn't create folder yet):

* `gh repo create repository_name --visibility --clone`
  (Replace `--visibility` with `private` or `public`)
* Then you can go into the newly created folder and follow instructions!

---

## 🔁 Create and Link Local Project to Remote (from the root of your project folder):

```bash
git init -b main
git add .
gh repo create repository_name --visibility # Don't need to do that if you did the last step `Repository Creation`
git commit -m "Your comments"
git remote add origin git@github.com:Username/repo_name.git
git push -u origin main
```

---

## 🗑️ Repository Deletion (from the root of your project folder):

* `gh repo delete repository_name --yes`

---

## ✅ All Set!

You just created your first repository without opening GitHub.com—well done!
You can read the [GitHub CLI Repository Management](./github_repo_managment.md) to learn how to manage your repositories directly from your local machine!

**📚 PS:** If you want to deepen your knowledge of Git and GitHub configuration, here are the links to the [Git Documentation](https://git-scm.com/docs), the [GitHub-CLI Documentation](https://cli.github.com/manual/), and the [GitHub Documentation](https://docs.github.com/en).

🚀 Feel free to check other [guides](../README.md) to learn more technos!
