# Tutorial Git Basics

# Create the repo and initialize it
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

# choose a path and clone the repo
cd /client/ && git clone /server/crud.git && cd crud

# config your user for commits records
git config --global user.name "test"
git config --global user.email "test@info.com"

# create a file, add to stage, commit, push to origin
touch README.md
git add README.md && git commit -m "initial commit" && git push origin main
```
