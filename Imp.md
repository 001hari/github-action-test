
Undo git add (unstage)....................git restore --staged file.txt
Discard local file changes....................git restore file.txt
Undo last commit but keep changes....................git reset --soft HEAD~1
Undo last commit and keep changes unstaged....................git reset --mixed HEAD~1
Completely erase last commit + changes....................git reset --hard HEAD~1
Undo a commit in a shared branch (safe)....................git revert