# Git commands

```bash
git log -p # shows the changed files with the changed lines

git log -p -2 # shows the last 2 commits in detail

git reset HEAD file.txt # put the file at untracked again

git checkout [branch_name or branch hash ID] # goes to some branch

sudo git checkout -b local origin/local # checkout to origin branch and create local branch

git reset HEAD~1 --soft # goes back one commit with the data to be commited
git push --force # then push force

git checkout -b [nome_branch] # creat branch, it creates the branch from the branch where you are

git branch # shows the branch name where you are

git branch -a # shows remote branches

git branch -d branch-name # remove delete branch local

# when you make a commit at branch master and update the same line at the same file
# in other branch, when you merge you will have a conflict to fix editing the file again
# at the master branch, accepting the new changes or not
git merge [branch_name] # make branches merge

# reset current merge
git reset --hard HEAD

git init --bare # run this command inside some folder that you want to use as local origin

git remoate add local shh://localhost/Users/gustavovinicius/Documents/baregit/ # add the baregit folder as the receiver of the local folder commits
git remote -v

# safe repo
git config --global --add safe.directory "$(pwd)"

sudo git diff master..local

sudo git diff master..local -- .env

git remote set-url origin [git repository http url with @ key]

git config -l | grep user
git config --global user.name "Your Name"
git config --global user.email "youremail@yourdomain.com"

# stash
git stash save [stash name]
git statsh list
git stash apply --index 0
git stash drop [stash ID]
for val in {3..1}; do git stash drop $val; done && git stash list

# Clean every change
sudo git clean -f --q .

# Local branch
git checkout -b network-scripting master
git add .
git commit -m "-test"
git push --set-upstream origin network-scripting

# Reset merge
git merge --abort

# Remove phantom file
git rm -f --cached ./path/file

# old clone with ssh
git clone git@github.com:GustavoViniciusdeMorais/Git_Basic_Commands.git

```
### Daily
```bash
echo $(date '+%Y-%m-%d')
git log --oneline --since="$(date '+%Y-%m-%d') 00:00:00" --until="$(date '+%Y-%m-%d') 23:59:59" --author="$(git config user.name)"
```
