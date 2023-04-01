# 6 Viewing the Changes Across Commits 1:30:00
- To see the changes between two commits ...

> git diff HEAD~2 HEAD

- Output the difference btw every file that has been changed accross these two commits .. 

# To see changes for a particular file 
- add the filename at the end of the command .... 

> git diff HEAD~2 HEAD <filename>
> git diff HEAD~2 HEAD file1.txt

# To see list of files that have been changed 

> git diff HEAD~2 HEAD --name-only

# To see how each file actually changed in the list of file

> git diff HEAD~2 HEAD --name-status

A       file2.txt
- means the file2.txt was added ... 
