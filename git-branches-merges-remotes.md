# Git: Branches, Merges and Remotes

__Tree-ish__

A directory containing files and other directories (which Git calls "trees") or any identifier which references a tree

A commit is considered tree-ish because it refers to a tree at the point when a commit has been applied.

e.g. 
- A directory
- A commit
- A reference

__SHA-1 Hash__

Git takes a changeset along with all of it's meta data and sends it into an SHA-1 Hashing algorithm and the result is a __complete 40-character string__  we can refer to this as the identifier for the commit.

## Configure Command Prompt

#### Git Prompt
- Add current branch name to command prompt
- Similar to .git-completion.bash
- https://github.com/git/git
	* contrib/completion/git-prompt.sh
- Save .sh to user directory

> __git_ps1_ - is the programmer function that installed by the script

## Reset Types
Reset changes the files in the staging index and/or working directory to the stat they had when a specifed commit was made

#### Soft Reset
- Moves HEAD pointer
- Does __not__ change staging index
- Does __not__ change working directory

Why?
> Return to an old state and leave code changes staged
> Useful for amending one ot more commits
> Similar to `git commit --amend`
> Previous commits will be discarded
> Be careful about amending commits which have been shared

#### Mixed Reset
- Moves HEAD pointer
- Changes staging index to match repository, you will changes in the staging index
- Does __not__ change working directory
- Default choice

Why? 
> Return to an old state and leave code changes in the working directory
> Useful for reordering commits
> Previous commits will be discarded
> Be careful about amending commits which have been shared

#### Hard Reset
- Moves HEAD pointer
- Changes Staging index to match repository
- Changes working directory to match repository

Why? 
> Return the an old state and discard all code changes 
> Useful to permanently undo commits 
> Previous commits and __all changes__ will be discarded 
> Be careful about amending commits which have been shared.

## Merge
- Always merge into master with a clean working directory
- Once merged the merged branch can be deleted

### Merge Types
- Fast-forward 
	* Just an extension of master
	
- True
	* Non fast forward

### Merge Conflicts

- Differenct  changes in two different branches on the same line
- Abort merge
- Resolve the conflicts manaually
- Use a merge tool

#### Strategy to Reduce Conflicts
- Keep lines short
- Keep commits small and focused
- Beware stray edits to whitespace (space, tabs, line returns)
- Merge often
- Master tracking

## Stash

- By default stash does not include untracked files and that is because there is no conflict
- Changes can be stashed for later retrieval and use
- When you either pop or apply your changes into your working directory it is possible of it to cause merge conflicts

## Fetch 

- Fetch before you work *This should be the first thing you do in the morning*
- Fetch before you push
- Fetch before you go offline
- Fetch often