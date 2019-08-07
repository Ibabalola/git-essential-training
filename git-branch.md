# Branches

#### Help 
`git help branch` To bring the help documentation for branching

#### commands
`git branch` to list all branches, by default will list all the master branch, currently checked out branch is coloured in green

`git branch {{branch_name}}` to create a branch, branch names should not have any spaces in them

`git checkout {{branch_name}}` to switch branches

`git checkout -b {{branch_name}}` to create a new branch and switch to it with the same command

`git branch --merged` to see which branches have been merged into the current branch

`git branch --no-merged` to see which branches have __not__ been merged into the current branch

`git branch -m {{old_branch_name}} {{new_branch_name}}` to move / rename a branch

`git branch -d {{branch_name}}` to delete a branch

`git branch -D {{branch_name}}` to force delete a branch

#### merge code
`git merge {{branch_name}}` will merge change from feature branch the current branch

`git merge --abort` to back out of the merge

`git mergetool` conflict resolution tool