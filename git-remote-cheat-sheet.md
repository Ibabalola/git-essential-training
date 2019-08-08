# Remote Cheat Sheet

`cat .git/config` to open the config file which has information about the remote branch (if any)

`git clone <URL> <directory name>` clone a respository held in GitHub

`git remote` list of the remotes that we have currently

`git remote add <origin name> <URL>`  add a remote with the url that relates to origin

`git remote rm <origin name>` to delete a remote

`git remote -v` shows what origin points to

`git push` pushes changes to our tracked remote origin repository

`git push -u <origin name> <branch name>` push to the origin remote to the master branch

`git push --set-upstream origin <feature_branch>` to push the current branch and sets up the remote as upstream

`git push --delete <origin name> <branch_name>` delete remote branch 

`git push <origin name> :<branch name>` going to delete the branch, remove this branch from the remote repository

`git fetch` will sync origin master with the remote, this will not change the HEAD pointer of the master branch

`git merge <origin name>` will bring all the fetched changes into your local master branch

`git pull` will fetch and merge the changes into your local master branch