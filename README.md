# Writing on file
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


##########################################################################

# Add local repo
git remote add origin <repo-url>

# Push the change to the master from origin
git push origin master

# Local master branch is link to remote master branch
git push --set-upstream origin master

