# The normal message for the status is very long ... 
Let's see a shorter message .... 
create a new file and update another file ... then check the status ... 

> echo newword >> file1.txt 
> echo hello > file2.txt 

> git status  
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   file1.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        file2.txt

no changes added to commit (use "git add" and/or "git commit -a")

# Now the short cut ... 
> git status -s 
 M file1.txt
?? file2.txt

- In this error message 
    - left col = staging area (
        red in color : change not added to staging area
        green color : ready to be committed 
        )
    - right col = working directory 

A = added 
M = modified 
D = deleted
