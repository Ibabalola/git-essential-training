Using Git version control software to manage project code

# Version Control 

__Purpose:__ Keeps track of changes
__Version Control System (VCS)__ 
__Source Code Management (SCM)__

# Histroy
__Source Code Control System (SCCS)__
1972: closed source, free with unix
Stored original verison and sets of changes

__Revision Control System (RCS)__
1982: open source
Stored latest version and sets of chages 

__Concurrent Version Control (CVS)__
1984 - 1990: open source
Multiple files, entire project
Multi - User repos 

__Apache Subversion (SVN)__
2000: open source
Track text and images
Track file changes collectively
 Use of revisions
 
__BitKepper SCM__ 
> Distributed version control
> "Community" version was free

__Git__
- April 2005
- Created by Linus Torvalds (Linux Terminal Creator)
- Open-source and free software 
- Compatible with Linux, macOS and Windows
- Faster
- Better safeguard against data corruption

# Distributed Version Control
- Different users maintain their own repositories
- No central respository
- Changes are stored as change sets

# Configuration
- __System__ 
	* /etc/gitconfig
	* Program Files\Git\etc\gitconfig
	* git config --system
	
- __User__
	* ~/.gitconfig
	* $HOME\.gitconfig
	* git config --global

- __Project__
	* my_project/.git/config
	* git config

# Where Git files are stored
Use ls -la to see hidden files in the command line

# Commit Message Best Practices
- A short single-line summary (less than 50 characters) 
- Keep each line to less than 72 characters
- Write commit messages in __present tense__, not past tense
	* e.g. "Fix for a bug" or "Fixes a bug" not "Fixed a bug"
	* Label for the changes within a commit
- Be clear and descriptive
	* Bad: "Fix typo"
	* Good: "Add missing hyphen in project section of HTML"
	* Bad: "Update login code"
	* Good: "Change user authentication to use Blowfish"

# The Three Trees
- Repository
- Staging Tree / Area
- Working Tree

# Git Workflow
Changes are made to the repository by a number of changesets, a snapshot of changes to our project.

- Uses a __checksum__ to identify each changeset, __checksum__ algorithm converts data into a simple number, it always returns the same result. Used to ensure data integrity.
- Uses the SHA-1 hash algorithm to create checksums
- 40 Character long **unique** string 
- To ensure data integrity each commit is linked to the last commit

# The HEAD Pointer
- Pointer to tip of current branch in repository
- Last state of repository, what was last checkout out
- Points to parent of next commit where writing commits takes place 
- The current position in the repository
- By default the branch we're working on is the master branch, that our main branch.

# Use .gitignore files
- Placed in the root of a project
- Specifies RE rules to tell git which files to never track
- Uses pattern matching e.g.
	* * ? [aeious][0-9]
	* logs/*.txt
- Negative expressions
	* *.php // ignore all files that end with .php
	* !index.php // but do not ignore index.php
- Ignore all files in a directory with a trailing slash
	* assets/videos/
- Comments
	* #This is a comment
- Blanks Lines are skipped

# Ideas on What to Ignore
- Compiled source code
- Packages and compressed files
- Logs and databases
- Operating system generated files
- User-uploaded assets (images, PDFs, videos)
- A collection of userful .gitignore templates
- https://github.com/github/gitignore

# Globally Ignore Files
- Ignore files in all respositories
- Settings are not tracked in respository
- User specific instead of respository specific