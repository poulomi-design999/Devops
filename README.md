# Gitflow Workflow Simulation

## 1. Initialize Repository and Create Branches
```bash
# Initialize Git Repository
mkdir zendriix-software-repo
cd zendriix-software-repo
git init

# Create develop branch
git checkout -b develop

# Create feature branch
git checkout -b feature/feature1 develop
git push origin feature/feature1
Develop a Feature and Merge It
# Work on feature branch
echo "Code for feature1" > feature1.txt
git add feature1.txt
git commit -m "Add feature1.txt for feature1"

# Merge feature branch into develop
git checkout develop
git merge feature/feature1
git push origin develop
Prepare for Release
# Create release branch
git checkout -b release/2025-01-25 develop
git push origin release/2025-01-25

# Prepare and finalize release
echo "Finalized code for release 2025-01-25" > release-notes.txt
git add release-notes.txt
git commit -m "Prepare release 2025-01-25"
Merge Release Branch into Master and Develop
# Merge release branch into master and tag release
git checkout master
git merge release/2025-01-25
git tag -a v2025-01-25 -m "Release 2025-01-25"
git push origin master
git push origin --tags

# Merge release branch into develop
git checkout develop
git merge release/2025-01-25
git push origin develop
Handle Urgent Hotfix
# Create hotfix branch
git checkout master
git checkout -b hotfix/urgent-fix

# Add urgent fix
echo "Urgent fix for production" > urgent.txt
git add urgent.txt
git commit -m "Add urgent.txt for hotfix"

# Merge hotfix branch into master
git checkout master
git merge hotfix/urgent-fix
git push origin master

# Merge hotfix branch into develop
git checkout develop
git merge hotfix/urgent-fix
git push origin develop


