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

## How to remove files from git commit
```bash
git reset --soft HEAD~1
git reset HEAD <filename> # remove <filename> from staging area
git commit --amend # commit changes again.
```

## Remove everything in git folder
```bash
git rm -r .
```

## How To Rename a Local and Remote Git Branch
Article: https://linuxize.com/post/how-to-rename-local-and-remote-git-branch/
```bash
git checkout <old_name>
git branch -m <new_name>
git push origin -u <new_name>
git push origin --delete <old_name>
```

## Squashing commits
https://www.internalpointers.com/post/squash-commits-into-one-git

## Push older commit to master without force push
If you want to avoid force pushing, here's how to revert your repo to an older commit and preserve all intervening work:
```bash
git checkout 307a5cd        # check out the commit that you want to reset to 
git checkout -b fixy        # create a branch named fixy to do the work
git merge -s ours master    # merge master's history without changing any files
git checkout master         # switch back to master
git merge fixy              # and merge in the fixed branch
git push                    # done, no need to force push!
```

## Git Reset 
https://devconnected.com/how-to-git-reset-to-head/

## How to update a forked repo with git rebase
```bash
git remote add upstream https://github.com/original-repo/goes-here.git
git fetch upstream
git rebase upstream/master
git push origin master #maybe: git push origin master --force
```

## How to "merge" specific files from another branch
```bash
git checkout <source_branch> <space-delimited paths>
```

## detached HEAD state
### You are here by accident or you want to discard your experimental changes:
```bash
git checkout <branch-name>
```
or with Git 2.23.0 and above:
```bash
git switch <branch-name>
```
### You made experimental changes and want to keep them
```bash
git branch alt-history
git checkout alt-history
```
