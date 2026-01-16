# My Git Project
✅ Part 1: Local Git Setup
Step 1: Install & Configure Git

# Check if Git is installed
git --version

# Configure global username & email
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"

# Verify configuration
git config --list

Step 2: Initialize Local Repository

# Create project directory
mkdir my-git-project
cd my-git-project

# Initialize Git repository
git init

# Check .git directory (hidden folder)
ls -la

Step 3: Basic Git Workflow

# Create files
echo "# My Git Project" > README.md
echo "console.log('Hello Git');" > script.js

# Check status
git status

# Stage files
git add README.md
# or stage all files
git add .
# or stage specific file
git add script.js

# Commit changes
git commit -m "Initial commit: Add README and script file"

# View commit history
git log --oneline

✅ Part 2: GitHub Integration
Step 4: Create GitHub Repository
1. Go to GitHub

2. Click "New repository"

3. Name: my-git-project

4. Don't initialize with README (since you already have one)

5. Create repository

Step 5: Connect Local to Remote
# Add remote repository (using HTTPS)
git remote add origin https://github.com/YOUR-USERNAME/my-git-project.git

# Verify remote
git remote -v

# Push to GitHub
git branch -M main
git push -u origin main

For SSH setup:-
# Generate SSH key
ssh-keygen -t ed25519 -C "your.email@example.com"

# Add SSH key to GitHub
# Copy key: cat ~/.ssh/id_ed25519.pub
# Add to GitHub Settings → SSH and GPG keys

# Use SSH URL instead
git remote set-url origin git@github.com:YOUR-USERNAME/my-git-project.git

✅ Part 3: Branching & Merging
Step 6: Branch Operations
# Create and switch to new branch
git checkout -b feature/add-login

# Make changes
echo "// Login functionality" >> script.js

# Commit feature changes
git add script.js
git commit -m "Add login functionality"

# Switch back to main
git checkout main

# Merge feature branch
git merge feature/add-login

# Delete feature branch
git branch -d feature/add-login

✅ Part 4: Rollback & History
Step 7: Practice Rollback
# View detailed history
git log --graph --oneline --all

# View specific commit
git show COMMIT_HASH

# Reset to previous commit (soft - keeps changes staged)
git reset --soft HEAD~1

# Reset (hard - discards changes)
git reset --hard COMMIT_HASH

# Revert (creates new commit undoing changes)
git revert COMMIT_HASH

# Checkout specific file from history
git checkout COMMIT_HASH -- filename.txt

