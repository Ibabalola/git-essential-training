# Revert

#### Undo Files
`git checkout -- {{filename}}` reverts the specified file to the version in the repository of the HEAD of the current branch

`git checkout -- .` reverts all files to the version in repository of the current branch

`git checkout {{SHA-1 Checksum}} -- {{filename}}` reverts the specified file to the version in the repository of the commit of the SHA-1 Checksum of the current branch

`git reset HEAD {{filename}}`  to remove files from the staged tree to the working tree

`git revert {{SHA-1 Checksum}}` reverts changes made in a commit

`git clean {{ -i | -n | -f }}` will remove untracked files, need to provide a flag

- i = interactive
- n = do a dry run, let's try this out, let's see what would happen
- f = runs the command, forces it to clean the files, do with caution 

## Reset

#### Soft Reset
`git reset --soft {{tree-ish}}`  

#### Mixed Reset
`git reset --mixed {{tree-ish}}`

#### Hard Reset
`git reset --hard {{tree-ish}}`