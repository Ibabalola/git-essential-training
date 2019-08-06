## Stash

`git stash save "{{name}}"` name is descriptive label to identify the stash
`git stash list` to view all stashes with the Git project 
`git stash show stash@{0}` returns a diff stat by default, to show what is in the stash
`git stash show -p stash@{0}` returns to show a patch of what is in the stash
