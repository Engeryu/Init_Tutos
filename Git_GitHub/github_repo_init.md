# 🛠️ GitHub CLI Repository Initialization:

If you don't know what `gh` is or can't execute it, check [README.md]()!

---

## 📁 Repository Listing (anywhere):

* `gh repo list`

---

## 🆕 Repository Creation (from the root of your project folder):

* `gh repo create repository_name --visibility --clone`
  (Replace `--visibility` with `private` or `public`)

---

## 🔁 Link Local Project to Remote (from the root of your project folder):

```bash
git init -b main
git add .
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
You can read [README.md]() to learn how to manage your repositories directly from your local machine!
