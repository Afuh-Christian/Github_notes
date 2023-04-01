#  Restoring a file to and earlier version
- When you keep tracks of files you , store every version of that file in git's database ...  

# We will delete one file and then restore the exact file .... 

> git rm file1.txt
> git commit -m "Deleted file1.txt"

# check the commits so we can know how to restore file1.txt
> git log --oneline
6396b1a (HEAD -> master) Deleted file1.txt
f38f0f0 Removed the bin directory that was accidentally committed
0ab0a98 Add gitignore
04e7d86 Remove unused code
3d7addc fix the bug that prevented the users from signing up
892f5af new file created
55f55e9 Initial commit


# Let's restore using the last but 1 commit ... since file1.txt is not found in that commit .... 

> git restore -h   .... to check all other commands we can use with it ... 

> git restore --source=<commitID> <filename or path to file>

# so .... 
>  git restore --source=f38f0f0 file1.txt

# chech status .. 
- you now have a new untracked file ... 
- you can use git add to add to staged area and so on ... 

