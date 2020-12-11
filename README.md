# GitHub: Initialize repo
```bash
echo "# README" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/gro1m/azure-dp100.git
git push --set-upstream origin main
```

# GitLab: Initialize repo

# Rollback
## Number 1
```bash
git revert --no-commit <commit-SHA-1 (first eight numbers)>..HEAD
git add .
git commit -m "<commit message>"
git push
```
## Number 2
```bash
git revert --no-edit <commit-SHA-1 (first eight numbers)>..HEAD
git push
```
## Number 3
```bash
git revert --no-commit HEAD~<number of commits>..
git add .
git commit -m "<commit message>"
git push
```
## Number 4
```bash
git revert --no-edit HEAD~<number of commits>..
git push
```
## Save configuration
```bash
cat >> ~/.gitconfig
[alias]
  rollback = "!git revert --no-commit $1..HEAD 
# Ctrl-D
git rollback <commit hash>
```
Examples of aliases:
- https://gist.github.com/johnpolacek/69604a1f6861129ef088
- https://www.durdn.com/blog/2012/11/22/must-have-git-aliases-advanced-examples/
