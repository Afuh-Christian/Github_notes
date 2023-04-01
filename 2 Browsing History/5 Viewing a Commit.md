# 5 Viewing a Commit 1:28:00


# Two ways .... TO VIEW A PARTICULAR COMMIT ..
# with ID  

# with HEAD  , HEAD~1 etc 
- 3rd to the last commit ..

> git show HEAD~2

- it shows everything about the commit , including the changes in the commit ... 

# we wish to see the final version of a file in  this commit ..

> git show HEAD~2:<path-to-file>

# we wish to see only the files that have been modified in a commit ... 

> git show HEAD~2 --name-only

- Outputs all the files that have been altered in the commit ...

# To get which was modified , added , deleted (More details ...)

> git show HEAD~2 --name-status

M = modified   
D = deleted   
A = added  


