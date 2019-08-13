# Git Intermediate Techniques

## Tag
- Tags allow marking points in history as important
- A named reference to a commit
- Most often used to mark releases (v1.0 v1.1 v2.0) 
- Can mark key features or changes
- Can mark points for team discussion

## Push Tags to a Remote
- Like branches, tags are local unless shared to a remote
- Tags must be explicitly transferred

## Stash

- By default stash does not include untracked files and that is because there is no conflict
- Changes can be stashed for later retrieval and use
- When you either pop or apply your changes into your working directory it is possible of it to cause merge conflicts

## Fetch 

- Fetch before you work *This should be the first thing you do in the morning*
- Fetch before you push
- Fetch before you go offline
- Fetch often

## Detached HEAD State 
- Checking out a commit puts the local repository in a "detached HEAD state"
- Like being on an unnamed branch
- New commits will not belong to any branch
- Detached commits will be garbages collected (~2 weeks)

## Interactive Staging
- Stage changes interactively
- Allows staging portions of changes files
- Helps to make smaller, focused commits
- Feature of many Git GUI tools

## Patch Mode
- Allows staging portions of a changed file
- "Hunk": an area where two files differ
- Hunks can be staged, skipped, or split into smaller hunks

## Edit a Hunk
- Can edit a hunk manually 
- Most useful when a hunk cannot be split automatically
- Diff-style line profixes: +, -, #, space

# Cherry-Picking Commits
- Apply the changes from one or more existing commits
- Each existing commit is recorded as a new commit on the current branch
- Conceptually similar to copy and paste
- New commits have different SHAs