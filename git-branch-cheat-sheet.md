# Branches

#### Help 
`git help branch` To bring the help documentation for branching

#### commands
`git branch` to list all branches, by default will list all the master branch, currently checked out branch is coloured in green

`git branch {{branch_name}}` to create a branch, branch names should not have any spaces in them

`git branch <branch name> <origin name>` used to check out remote branches to create a local copy

`git checkout {{branch_name}}` to switch branches

`git checkout -b {{branch_name}} {{origin name}}` to create a new branch and switch to it with the same command

`git branch --merged` to see which branches have been merged into the current branch

`git branch --no-merged` to see which branches have __not__ been merged into the current branch

`git branch -m {{old_branch_name}} {{new_branch_name}}` to move / rename a branch

`git branch -d {{branch_name}}` to delete a branch

`git branch -D {{branch_name}}` to force delete a branch

`git branch -r` shows our remote tracking branches

`git branch -a` shows us all of our branches, both remotes and local

`git branch -u <origin name>/<branch name> <branch name>` use to set an upstream for a branch

#### merge code
`git merge <branch_name>` will merge change from feature branch the current branch

`git merge --abort` to back out of the merge

`git mergetool` conflict resolution tool

`git merge <origin name>` will bring all the fetched changes into your local master branch

#### Prune

`git remote prune origin` to used to delete the remote tracking branch, the snapshot of the remote branch add `--dry-run` to see what it will do / look like

`git prune` removes all unreachable objects