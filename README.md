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

## Git global setup
```bash
git config --global user.name "MMM"
git config --global user.email "mmm@whateveryourprovideris.com"
```

## Create a new repository
```bash
git clone <git https address>.git
cd <directory of cloned git repo>
touch README.md
git add README.md
git commit -m "add README"
git push -u origin master
```

## Push an existing folder
```bash
cd existing_folder
git init
git remote add origin <git https address>.git
git add .
git commit -m "Initial commit"
git push -u origin master
```

## Push an existing Git repository
```bash
cd existing_repo
git remote rename origin old-origin
git remote add origin  <git https address>.git
git push -u origin --all
git push -u origin --tags
```

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


Check once: https://blog.tomasfejfar.cz/git-how-to-make-master-empty/
