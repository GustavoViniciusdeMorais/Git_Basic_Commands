# Tutorial Git Basics

### Create the repo and initialize it
```bash
# update OS and install git
apt update -y && apt install git -y

# create regular folder
mkdir /server/crud.git && cd /server/crud.git

# make it a central hub for others to pull/push
git init --bare

# change main branch name if needed
git branch -m main
git branch --show-current
ls -lha

# verifies if dir is a git bare
git rev-parse --is-bare-repository

# check working being done with
git show -q [branch name]
git log [branch name] -p -1

# choose a path and clone the repo
cd /client/ && git clone /server/crud.git && cd crud

# config your user for commits records
git config --global user.name "test"
git config --global user.email "test@info.com"
git config --list | grep user

# create a file, add to stage, commit, push to origin
touch README.md
git add README.md && git commit -m "initial commit" && git push origin main
```
### Create new branch
```bash
git checkout -b [new branch name] main
git push --set-upstream [remote name] [new branch name]
git remote show [remote name] | head -10
git push [remote name] [new branch name]
```
### PHP Example
```php
<?php
function sum(?int $a = 0, ?int $b = 0)
{
    return $a + $b;
}
echo sum($argv[1] ?? 1,$argv[2] ?? 1);
echo "\n";
```
### Merge
```bash
git merge feature2
```
### Manage remotes
```bash
git remote add [remote name] /server/backup.git/
git push --set-upstream [remote name] [new branch name]
git push [remote name] [branch name]
```
### Revert changes
```bash
git log --oneline | head -3
# just see the files of commit
git checkout [hash commit]
git revert HEAD # undo last commit
# --soft goes back with data to be commited
git reset HEAD~1 --hard # undo the undo
# goes back to remove code
git reset --hard [hash commit]
# if want overwrite
git push [remote name] [branch name] --force
```
