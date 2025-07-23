
# 📝 Git Practice on AWS EC2 – From Configuration to Conclusion

## ⚙️ 2. Git Configuration

```bash
git config --global user.name "YourName"
git config --global user.email "YourEmail@example.com"
```
Explanation: Sets your identity for Git commits.

```bash
git config --list
```
Explanation: View all Git configurations.

---

## 📁 3. Git Initialization & Setup

### Step 1: Create a directory for your repo
```bash
mkdir myproject
cd myproject
```

### Step 2: Initialize a Git repo
```bash
git init
```
Explanation: Starts a new Git repository in the current directory.

---

## 🔁 4. Adding Files and Committing

```bash
cat > file1.txt
# Write some content and press Ctrl+D
git status           # Shows changes
git add .            # Stages all changes
git commit -m "Initial commit"
```

Explanation:
- `git status` shows which files are staged, unstaged, or untracked.
- `git add .` adds all new/modified files to the staging area.
- `git commit -m` saves the snapshot permanently in Git history.

---

## 🌐 5. Connecting to Remote GitHub Repository

### Step 1: Add the remote repo
```bash
git remote add origin https://<your-token>@github.com/<username>/<repo-name>.git
```

### Step 2: Push the code
```bash
git push -u origin master
```
or if the branch is `main`:
```bash
git push -u origin main
```

Explanation:
- `-u` sets the upstream tracking, so future pushes can be done with just `git push`.

---

## 🔄 6. Pulling Changes from Remote

```bash
git pull origin main
```
or
```bash
git pull origin master
```
Explanation: Downloads and integrates changes from the remote repository.

---

## 📜 7. Git Log Commands

```bash
git log            # Detailed commit history
git log -1         # Last commit only
git log -2         # Last 2 commits
git log --oneline  # Concise log view
git log --grep "keyword"
```

---

## 🚫 8. Ignore Files Using `.gitignore`

```bash
vi .gitignore
# Add file extensions or names to ignore
*.log
*.class
*.env
```
Then:
```bash
git add .gitignore
git commit -m "ignored file format"
```

---

## 🔁 9. Changing or Removing Remote

```bash
git remote remove origin
git remote add origin https://github.com/username/repo.git
git remote set-url origin <new-url>
```
Explanation: Useful if you make a mistake or want to change your repository location.

---

## ❌ 10. Common Errors and Fixes

| Error | Cause | Fix |
|------|-------|-----|
| `Could not resolve host` | Wrong URL or missing `.git` | Double-check your remote URL |
| `src refspec main does not match any` | Branch `main` doesn’t exist locally | Use `master` or create `main` |
| `No such remote 'origin'` | Remote not set | Use `git remote add origin <url>` |

---

## ♻️ 11. Resetting and Cleaning Working Directory

### Reset hard to discard staged changes
```bash
git reset --hard
```
Explanation: Discards all staged changes and resets the working directory to the last commit.

---

## 🗑️ 12. Deleting Files

```bash
rm file4.java
rm file3.css
```
Explanation: Deletes files from the file system (use with caution).

---

## ✍️ 13. Reverting Commits

### Step 1: Make and commit changes
```bash
cat > revertfile
# Add some content
git add .
git commit -m "first code commited"

cat >> revertfile
# Add more content
git add .
git commit -m "second code commited"
```

### Step 2: Revert a commit
```bash
git revert <commit-hash>
```
Explanation: This creates a new commit that undoes the changes made by the specified commit.

---

## 🧹 14. Cleaning Untracked Files

```bash
git clean -n   # Preview what will be deleted
git clean -f   # Force delete untracked files
```

Explanation:
- `git clean -n`: Lists untracked files that would be removed.
- `git clean -f`: Actually removes them.

---

## ✅ Conclusion

This practice covers:
- Git configuration
- Local repo creation and initialization
- Committing and tracking files
- Connecting to GitHub
- Pushing/pulling changes
- Handling commit history and logs
- Ignoring files and remote management
- Reverting commits and cleaning untracked files
- Troubleshooting common Git errors

You're now well-equipped with both basic and advanced Git operations. Keep practicing and pushing code! ✅
