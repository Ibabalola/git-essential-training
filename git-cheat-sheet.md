# Git

## Version
`git version`  states the version of Git installed.

## Help 
`git help` A very useful tool for finding out how to use Git
`git help ${{command}}` - For detailed help about a command

## Where is Git installed
`which git`  locates the directory where Git is installed 

## Remote Repositories
`git remote -v` list of remotes for a Git repository
`git remote add origin {{Repo URL}}` adds a remote origin for your local Git repo
`git push -u origin master` push the content to the remote repo

## Information
- Git does not track empty directories
- To track empty files place a .gitkeep file with empty directories
 
`git status` lists the file changes with the working and staging trees
`git ls-tree HEAD` listing the files in the tree`

i.e.
`100644 blob 246eb07d07054f65379d74492142bd18c33ab9ea    .babelrc
100644 blob 93dd0d28e6fc672981b4e16411fff7f5ffa578a2    .editorconfig
100644 blob 588f79af6d2a4ae73b000e5a8ef12b82605feb08    .eslintignore
100644 blob 79035e1ac42e016454aec56364dfa0a273e910ba    .eslintrc.js
100644 blob b66c953bf77954fc5cd4ea49c16c9daa0c090744    .gitignore
040000 tree a5fc9b96caebfde1f3f209cce044038c148c5471    .vscode
100644 blob 02f52fcfe83d14824dda5152467156f991e1fdd4    README.md
040000 tree a74c70ccf250ec0604c63c2be0870fc4a04f834e    config
100644 blob fa7e01d067a3e47b69326abc3193170183c62431    package-lock.json
100644 blob 4a807d42818016972e0b907b7b58dd33249a7aa2    package.json
100644 blob 74aec7e60cfd3230382edd07e6a0acdccb696ecf    prettier.config.js
040000 tree c018d9f825b3eabc6572123bdd6a576c2bcf734e    server`

## Configurations 
`git config --system`
`git config --global`
`git config --list`
`git config user.name` // isaac.babalola
`git config --global core.editor "notepad.exe -wl1"` // pause and wait b4 proceeding
`git config --global core.editor "atom --wait"` // boot n wait 4 git to tell it what to do
`git config --global color.ui true`
`git config --global core.excludesfile ~/.gitignore_global` // what files should be used for exclusions for and any directory

> Can be placed anywhere 
> Can have any name
> Ideally in your user directory C:\Users\isaac.babalola

## Commands

#### Add Files
`git add .` where . refers to the current directory, changes are not permenant not tracking
`git add {{name}}*` where * refers to a wildcard character to match all changed files in the working tree 

#### Delete Files
`git rm {{file_name}}`   deletes the specified file from the working tree and the index
`git rm --cached {{file_name}}` deletes the files from the staging tree / index

#### Move / Rename files
`git mv {{file_name}} {{new_file_name}}` can also be used to move a file to a new location / directory

#### Diff Files
`git diff {{filename}}` - call the diff program on our code
`git diff --staged` show us the changes within the files of our staged area
`git diff --cached` show us the changes within the files of our staged area
`git diff --color-words` shows only the words that are different, helps to zero in on the change
`git diff {{Older SHA-1 Checksum}}..{{Newer SHA-1 Checksum}} --color-words` show the diff between to different commits that are not sequential

> SPACE BAR to see another change
> @@ {{ Line Number }} {{ Number of Lines }} @@ ~ configurable
> Uses paginator, F to go forward, B to go backward
> -S to change text wrapping and to switch back
> q to quit / exit paginator

#### Show Files
`git show {{SHA-1 Checksum}} --color-words` - 6 - 9 characters is enough for the SHA-1 Checksum, show the diff of a past commit

#### Undo Files
`git checkout -- {{filename}}` reverts the specified file to the version in the repository of the HEAD of the current branch
`git checkout -- .` reverts all files to the version in repository of the current branch
`git checkout {{SHA-1 Checksum}} -- {{filename}}` reverts the specified file to the version in the repository of the commit of the SHA-1 Checksum of the current branch
`git reset HEAD {{filename}}`  to remove files from the staged tree to the working tree
`git revert {{SHA-1 Checksum}}` reverts changes made in a commit
`git clean {{ -i | -n | -f }}` will remove untracked files, need to provide a flag

> i = interactive
> n = do a dry run, let's try this out, let's see what would happen
> f = runs the command, forces it to clean the files, do with caution 

#### Commit Files
`git commit -m "{{message}}"`  files are now tracked
`git commit -am` (same as below) and add a message
`git commit -a` skips the add to staging step, adds all __tracked__ files to the repository
`git commit --all` skips the add to staging step, adds all __tracked__ files to the repository
`git commit -amend -m "{{message}}"` to change / include changes into a previous commit

> `git commit -a` an absence of -m allows multiline commit messages that can be made in an editor
> `--allow-unrelated-histories` to force the merge to happen.

#### Loging
`git log -n 5` returns the 5 most recent commit logs 
`git log --since=2019-01-01` returns commits since a certain date
`git log --until=2019-01-01` returns commits until a certain date
`git log --author="Isaac"` returns commits by an author
`git log --grep="{{RE}}"` returns commits that have a commit message that match a regular expression
`git log --oneline` gives the file line of each commit



