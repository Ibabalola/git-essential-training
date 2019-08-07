# Stash

`git stash save "{{name}}"` name is descriptive label to identify the stash

`git stash list` to view all stashes with the Git project

`git stash show stash@{n}` returns a diff stat by default, to show what is in the stash

`git stash show -p stash@{n}` returns to show a patch of what is in the stash

`git stash pop` by default returns the first stash in the list, alternatively you can provide a stash@{n} to get a specific stash

`git stash apply` bring changes into the working directory but keeps the stash changes

`git stash drop stash@{n}` used to delete a particular stash

`git stash clear` remove all items from the stash