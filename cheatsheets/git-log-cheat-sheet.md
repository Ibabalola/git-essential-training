# Git Log

`git log -n 5` returns the 5 most recent commit logs

`git log --since=2019-01-01` returns commits since / after a certain date

`git log --until=2019-01-01` returns commits until a certain date

`git log --until="3 days ago"` returns commits until a certain date

`git log --after=2.weeks --before=3.days` specifying a period of time

`git log --author="Isaac"` returns commits by an author

`git log --grep="{{RE}}"` returns commits that have a commit message that match a regular expression

`git log --oneline` gives the file line of each commit

`git log {{SHA-1 Checksum}}..HEAD` returns the all the commits between each treeish object

`git log {{file-name}}` to ask Git to focus on commits on a specified file

`git log -p` -p is for patch, a patch is the same thing as a changeset, what is the patch that will change the repository from one conditions to another

`git log --stat` will show you statistics about what was changed in each commit

`git log --format={{format}}`  e.g. oneline | short | medium (default) | full | fuller | email | raw

`git log --graph` Git graphs out all the commits - useful for display of branches

`git log --graph --all --oneline --decorate` Useful for visualizing branches