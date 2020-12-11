# GitHub: Initialize repo

echo "# README" >> README.md

git init

git add README.md

git commit -m "first commit"

git branch -M main

git remote add origin https://github.com/gro1m/azure-dp100.git

git push --set-upstream origin main

# GitLab: Initialize repo

# Rollback
git revert --no-commit <commit-SHA-1 (first eight numbers)>..HEAD -> git add . -> git commit -m "<commit message>" -> git push
git revert --no-edit <commit-SHA-1 (first eight numbers)>..HEAD
git revert --no-commit HEAD~<number of commits>..
git revert --no-edit HEAD~<number of commits>.. -> git add . -> git commit -m "<commit message>" -> git push
