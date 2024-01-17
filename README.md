# Switch to dev branch for ongoing development
git checkout dev

# Create a new feature branch
git checkout -b feature/new-feature

# Work on the feature and commit changes
git commit -m "Implement new feature"

# Merge the feature branch into dev
git checkout dev
git merge --no-ff feature/new-feature

# Create a release branch at the beginning of the month
git checkout -b release/2024-02

# Test and fix any issues in the release branch
# Once testing is successful, merge into master and dev
git checkout master
git merge --no-ff release/2024-02
git tag -a v2024-02 -m "Release 2024-02"

git checkout dev
git merge --no-ff release/2024-02

# Repeat the process for subsequent months
