# github-basics-and-commands
A cheat sheet/notes of all the git hub commands required from terminal to push or change the code in github.com


# Git & GitHub Cheat Sheet for Beginners
*All essential commands explained in plain English*

---

## 📋 **1. ONE-TIME SETUP**

```bash
# Tell Git who you are (do this once on any computer)
git config --global user.name "Your Name"
git config --global user.email "your@email.com"
```


## 🚀 **2. NEW PROJECT SETUP**

```bash
# Step 1: Start tracking your folder
git init

# Step 2: Create .gitignore (what NOT to upload)
echo "venv/" > .gitignore  # For Python virtual environments
echo ".DS_Store" >> .gitignore  # Mac hidden files

# Step 3: Take snapshot of all files
git add .

# Step 4: Save the snapshot with a message
git commit -m "First commit"

# Step 5: Connect to GitHub (get URL from GitHub.com)
git remote add origin https://github.com/YOURNAME/PROJECT.git

# Step 6: Upload to GitHub
git push -u origin main
```

## 📝 **3. DAILY WORKFLOW**

```bash
# Check what you changed
git status

# Add specific file
git add filename.py

# Add ALL changed files
git add .

# Save snapshot with message
git commit -m "Fixed login bug"

# Upload to GitHub
git push
```


## 🔄 **4. SYNCING WITH GITHUB**

```bash
# Download latest from GitHub
git pull origin main

# Upload your changes
git push

# Check if connected
git remote -v
```

## ⚠️ **5. WHEN THINGS GO WRONG**
```bash
# Undo last commit (keep changes)
git reset --soft HEAD~1

# Discard changes in a file
git checkout -- filename.py

# See your commit history
git log --oneline

# Force push (careful! overwrites GitHub)
git push --force origin main
```

## 🌿 **6. BRANCHES (Optional but useful)**
```bash
# Create new branch
git checkout -b feature-branch

# Switch back to main
git checkout main

# Merge branch into main
git merge feature-branch

# Delete branch
git branch -d feature-branch
```

## 🔧 **7. REBASE COMMANDS (Advanced)**
```bash
What is Rebasing?
Think of it as "rewriting history" to make it cleaner. Use only when your local changes and GitHub changes diverged.

# Pull with rebase (instead of regular pull)
git pull origin main --rebase

# If conflicts appear during rebase:
# 1. Fix conflicts in VS Code
# 2. Then continue:
git add .
git rebase --continue

# Cancel rebase if too confusing
git rebase --abort

When to use rebase:
When you edited BOTH locally AND on GitHub.com

When you want clean, linear history

When working with others on same branch

When to avoid rebase:
Just learning Git

Working alone

Don't care about perfect history
```

## 🎯 **8. GITHUB.COM VS VS CODE SCENARIOS**
```bash
Scenario 1: You edited on GitHub.com directly

# Download GitHub changes first
git pull origin main

# Now push your VS Code changes
git push


Scenario 2: Merge Conflict (both edited same file)
Git will show "CONFLICT"

Open file in VS Code - you'll see both versions

Choose which changes to keep

Then:
git add filename.py
git commit -m "Fixed merge conflict"
git push
```

## 📊 **9. ESSENTIAL COMMANDS QUICK REFERENCE**

```bash
Command                |  	What it does	            When to use
-----------------------------------------------------------------------
git status	               See what changed	        Before doing anything
git add .	                 Stage all changes	      Ready to commit
git commit -m "msg"	       Save snapshot	          After adding files
git push	                 Upload to GitHub	        After committing
git pull	                 Download from GitHub	    Start of work session
git log --oneline	         See history	            Check what you did
git diff	                 See exact changes	      Before committing

```

## 💡 **10. GOLDEN RULES**
```bash
ALWAYS run git status first

NEVER commit without .gitignore (especially venv/)

Commit often - small changes are better than big ones

Clear commit messages: "Fixed login bug" NOT "updated stuff"

Pull before push if others might be working on it

One feature = One commit when possible
```



## 🗂️ **11. PROJECT STRUCTURE**
```bash
my-project/
├── venv/           # Virtual environment (IGNORED)
├── .gitignore      # Tells Git what to ignore
├── requirements.txt # Python dependencies
├── main.py         # Your code
└── README.md       # Project documentation
```

## 🆘 **12. EMERGENCY FIXES**
```bash
# Completely start over (nuclear option)
rm -rf .git          # Delete local Git history
git init            # Start fresh
git add .           # Add all files
git commit -m "Fresh start"
git remote add origin YOUR-URL
git push --force origin main  # Overwrite GitHub
```
## 🎮 **VISUAL METAPHORS**
```bash
git add = Put items in a cardboard box

git commit = Tape box shut and label it

git push = Ship box to Amazon warehouse (GitHub)

git pull = Get deliveries from warehouse

branch = Make a copy to experiment on

rebase = Rewrite shipping labels to look neat
```

## ✅ **BEGINNER'S WORKFLOW CHECKLIST**

```bash
Create project folder

git init

Create .gitignore with venv/

git add .

git commit -m "First commit"

Create repo on GitHub.com (no README!)

git remote add origin YOUR-URL

git push -u origin main

Make changes in VS Code

git add .

git commit -m "Description"

git push

```bash

** Remember: Git is just fancy "Save As" with history. GitHub is cloud storage for those saves. That's it!**
