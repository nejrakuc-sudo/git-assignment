# Git Assignment

git config --global user.name "Nejra Kuc"
git config --global user.email "nejra.kuc@stu.ibu.edu.ba"

# Verify configuration
git config --list

# Create project folder and initialize Git
mkdir git-assignment
cd git-assignment
git init

# Create README and commit
echo "# Git Assignment" > README.md
git add README.md
git status
git commit -m "Initial commit: Added README file."
git log --oneline

# Add remote repository
git remote add origin https://github.com/nejrakuc-sudo/git-assignment.git
git remote -v

# Push main branch to GitHub
git push -u origin main
# Create feature branch and commit changes
git checkout -b feature-A
echo "Working on feature A" >> README.md
git add README.md
git commit -m "FEAT: Added content for feature A"

# Switch to main and commit a hotfix
git checkout main
echo "Hotfix change directly on main" >> README.md
git add README.md
git commit -m "HOTFIX: Quick update directly on main"

# Rebase feature-A onto main
git checkout feature-A
git rebase main

# Resolve merge conflict manually in README.md
nano README.md   # edit file to resolve conflict
git add README.md
git commit --no-edit
git rebase --continue

# Push rebased branch to GitHub
git push origin feature-A --force
# Switch to main and create development branch
git checkout main
git checkout -b development

# Create feature-C branch, add file, and commit
git checkout -b feature-C
echo "This is feature C" > feature_c.txt
git add feature_c.txt
git commit -m "FEAT: Completed feature C"

# Create feature-D branch, add file, and commit
git checkout development
git checkout -b feature-D
echo "This is feature D" > feature_d.txt
git add feature_d.txt
git commit -m "FEAT: Completed feature D"

# Merge feature branches into development
git checkout development
git merge feature-C
git merge feature-D

# Push development branch to GitHub
git push origin development

# View repository history
git log --oneline --graph --all

![Phase 1 Screenshot](screenshots/1)
![Phase 1 Screenshot](screenshots/2)
![Phase 1 Screenshot](screenshots/3)
![Phase 1 Screenshot](screenshots/4)
![Phase 1 Screenshot](screenshots/5)
