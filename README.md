Git repository?
- place to store file or folders.
- easy to do the version control

1) Remote repository: save the files on server. you can share with others.<br>
2) Local repository: save the files on my local computer.<br>

# Workflow
- commit: taking a snapshot of our project
- staging area  = index: area in between our project repo and git repo. Reviewing our modified files before we permannently stored snapshots into our git repo. 
- Push: update from local repo to remote repo
- Clone: cloning files from remote repo
- Pull: update from remote repo to local repo
- Merge: if somebody made change and push, it reject my push.
- Conflict: if others and I change the same line of the code.
- Stash: Before creating a new branch, temporary stored the changes into other area.
You can bring it back later to the branch.  

Branch Types
- Integration Branch
- Topic Branch = feature branch: use for fixing bug. branch from develope branch, merge into develope branch after done.

Merge
- Fast-forward merge: master branch didn't make any change since it create the other branch
- Not fast-forward merge 
- rebase: merge into one, remove the other branch 


## Basic
```python
# Create & Write on file
echo hello > file1.txt
echo hello > file2.txt

# Check status
git status

# Add to staging area
git add files1.txt files2.txt
git add *.txt
git add .

# Modified file1
echo world >> file1.txt

# Add modified file
git add file1.txt

# Permanent store file into git repo
git commit -m "Initial commit."

# Skipping staging area
echo test >> file1.txt
git commit -am "fix the bug"

# Remove a file both from working direc and staging area
git rm file2.txt
git commit -m "Remove file2."

# Remove entire directory from the staging area
mkdir bin
echo hello > bin/app.bin
git status
git add .
git commit -m "Add bin."
git rm --cached -r bin/

# Renaming & Moving
git mv file1.txt main.js 
git commit -m "Refactor code."

# Ignoring files
mkdir logs
echo hello > logs/dev.log
.gitignore                  # create file
echo logs/ > .gitignore     # ignore log files
git add .gitignore          # add to staging area
git commit -m "Add gitignore"

# Check git status short
git status -s
---RED = in working directory
---GREEN = in staging area
---M = modified
---A = added

# Check the different area
git diff --staged
git diff

# Diff tools
git config --global diff.tool vscode
git config --global diff.tool.vscode.cmd "code --wait --diff $LOCAL $REMOTE"
git config --global -e
```

## Branch
```python
# Add
git branch <new-branch>
git push --set-upstream <new-branch> <new-branch> # set remote as upstream
# Switch
git checkout <branch>
# Add + Switch
git checkout -b <new-branch>
# Merge
git merge <branch>
# Delete
git branch  -d <branch>
# List of current branches
git branch
git branch -a       # both remote branches and local branches.
git branch -v       # last commit on each branch
git branch --merged # merged branches
git branch --no-merged
# Delete
git push -d origin new_branch
git push -d <name-of-remote-repository> <branch-name>
```

## Remote
```python
# Add
git remote add <new-remote> <repo-url>
git remote add new https://github.com/dana6691/apache_airflow.git
# Check remote name
git remote
git remote -v
# Inspecting
git remote show origin
# Push the change of branch to your remotes
git push <remote> <branch>
git push origin master
# Renaming & Removing
git remote rename origin paul
git remote remove paul
# Fetch: move from remote to local repo
```
## Fetch
```python
# pull all remote branchs
git fetch --all
```