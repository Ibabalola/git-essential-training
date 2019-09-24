# Git Cheat Sheet

## Version
`git version`  states the version of Git installed.

## Help 
`git help` A very useful tool for finding out how to use Git

`git help ${{command}}` - For detailed help about a command

## Where is Git installed
`which git`  locates the directory where Git is installed 

## Information
- Git does not track empty directories
- To track empty files place a .gitkeep file with empty directories
 
`git status` lists the file changes with the working and staging trees

`git ls-tree {{tree-ish}}` listing the files in the tree, e.g. git ls-tree HEAD

i.e.
-  List of Identifiers 
-  A tree here is directory
-  blob => files which means Binary Large Object
-  This list give us a view of the tree at the specified time of the commit
-  the {{tree-ish}} uses patern matching, adding a / gives us visibility of the content in side a tree

```
100644 blob 246eb07d07054f65379d74492142bd18c33ab9ea    .babelrc
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
040000 tree c018d9f825b3eabc6572123bdd6a576c2bcf734e    server
```

`cat .git/HEAD` to find out which commit the HEAD pointer is pointing to, also indicate which branch the HEAD pointer is on

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

`git config --global alias.praise blame` to change to alias of blame to praise

## Commands

#### Add Files
`git add .` where . refers to the current directory, changes are not permenant not tracking

`git add {{name}}*` where * refers to a wildcard character to match all changed files in the working tree 

`git add --interactive` to enter interactive staging mode or `-i` for short

`git add --patch` to add a hunk to the staged tree `-p` for short

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

`git diff {{Older commit}}..{{Newer commit}} --color-words` show the diff between to different commits that are not sequential

`git diff {{treeish}}..{{treeish}}` any treeish object can be compared even branches

`git diff {{from-commit}} {{to-commit}} > output.diff` to create a diff patch to a file (.diff)

`git apply {{filepath}}` to apply a patch

`git am feature/0001-some-name.patch` Apply single patch

`git am feature/*.patch` Apply all patches in a directory

`git format-patch {{commit}}..{{commit}}` creates individuals files for each commit

`git format-patch {{branch}}` export all commits on current branch which are not in master branch

`git format-patch -1 {{SHA}}` Export a single commit

`git format-patch {{branch}} -o feature` put patch files into a directory 

`git format-patch {{commit}}..{{commit}} --stdout > feature.patch` Output patches as a single file

- SPACE BAR to see another change
- @@ {{ Line Number }} {{ Number of Lines }} @@ ~ configurable
- Uses paginator, F to go forward, B to go backward
- -S to change text wrapping and to switch back
- q to quit / exit paginator

#### Show Files
`git show {{commit}} --color-words` - 6 - 9 characters is enough for the SHA-1 Checksum, show the diff of a past commit

- adding carat symbol after a SHA-1 Checksum points to the parent commit on any tree-ish reference e.g. {{commit}}^
- adding two carat symbols after a SHA-1 Checksum tells Git to go to the Grandparent e.g. {{commit}}^^
- adding tilde symbol plus a number tell Git to go back n generations e.g. HEAD~1, HEAD ~ has the same effect because the default nuumber for n is 1

#### Commit Files
`git commit -m "{{message}}"`  files are now tracked

`git commit -am` (same as below) and add a message

`git commit -a` skips the add to staging step, adds all __tracked__ files to the repository

`git commit --all` skips the add to staging step, adds all __tracked__ files to the repository

`git commit -amend -m "{{message}}"` to change / include changes into a previous commit

`git commit -a` an absence of -m allows multiline commit messages that can be made in an editor

`--allow-unrelated-histories` to force the merge to happen.

#### Tags

`git tag <tag name> <commit>` add a lightweight tag

`git tab <tag name> -am "<message>" <commit>` add an annotated tag (most common)

`git tag --list` list all tags use `-l` for a shortcard 

`git tab -l <Regular Expression>` to filter the tags

`git tab -l -n` list tags with annotations

`git tag --delete <tag name>` to delete a tag use `-d` for shortcode

`git push <origin name> <tag name>` to push a tag to a remote server

Delete remote tags like remote branches

```
git push origin :<tag name>
git push --delete origin <tag name>
git push -d origin <tag name>
```

`git push origin --tags` to push all tags to a remote server

`git fetch --tags` fetch only tabs (with necessary commits)

`git checkout -b <branch name> <tag name>` creates a new branch from the commit the tag points to

`git checkout <tag name>` checkouts a new tag directly by moving the HEAD pointer

#### Cherry Pick
`git cherry-pick <SHA-Check Sum>` to cherry pick a change made in a particular commit

`git cherry-pick <SHA Check Sum>..<SHA Check Sum>` to specify a range of commits

#### Blame
`git blame -w <filename.txt>` Annotate file with commits details -w to ignore whitespaces

`git blame -L 5,10 <filename.txt>` to show a certain number of lines within a file

`git annotate <filename.txt>` similar information to git blame but in a different formate

#### Bisect
`git bisect start` to start a bisect session

`git bisect bad <treeish>` last known bad 

`git bisect good <treeish>` last known good 

`git bisect reset` reset to your working directory back to head your was at before you started bisecting.