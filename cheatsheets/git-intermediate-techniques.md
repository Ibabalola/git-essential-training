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

# Create Diff Patches
- Share changes via files
- Useful when changes are not ready fora public branch
- Useful when collaborators do not share a remote
- Discussion, review, approval process

# Apply Diff Patches
- Apply changes in a diff patch file to the working directory
- Makes changes, but not commits
- No commit history transferred

# Create Formatted Patches
- Export each commit un Unix mail format
- Useful for email distribution of changes
- Includes commit message
- One commit per file by default

# Apply Formatted Patch
- Extract author, commit message, and changes from a mailbox message and apply them to the current branch
- Similar to cherry-picking: same changes different SHAs
- Commit history is transferred

# Rebase Commits
- Take commits from a branch and replay them at the end of another branch
- Useful to integrate recent commits without merging
- Maintains a cleaner, more linear project history
- Ensures topic branch commits apply cleanly

# Blame
- Browse an annotated file
- Determine who changed which lines in a file and why
- Useful for probing the history behind a file's contents
- Useful for identifying which commit introduced a bug

# Bisect
- Find the commit that introduced a bug or regression
- Mark last good revision and first bad revision
- Resets code to mid-point
- Marks as good or bad revision
- Repeat