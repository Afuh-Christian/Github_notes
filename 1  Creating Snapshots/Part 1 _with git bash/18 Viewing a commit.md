# We wish to see what we have changed in a given commit 

> git show <id of commit>

# to show last commit 

> git show HEAD 

# to show last but 1 commit 

> git show HEAD~ 

# to show last but 2 commit 

> git show HEAD~1 

> git ls-tree HEAD~1

# if we wish to see the final version stored in a commit ... 

> git show HEAD~1:<path to file from current direcory> 

> git show HEAD~1:.gitignore










# To see all the files and directories in a commit ...

> git ls-tree HEAD~1

- ls-tree  = to see all the parent dirs and files ..
# ...OUTPUT 
100644 blob 51912609ec27972cefdb1287cf1c5c9fe284b0f5    .gitignore
100644 blob 4ffc87365261b5cb2b2972f98d58f3e468fbaa57    file1.txt
# ....Output ......

# NB  Data types of : 
- files = blob ,
- folders(directorues) = tree ....
        are all stored in git's database ... 


# we can also use "git show <ID>"  to display the contents of any of the files above ... 
# with this command , we can view and object in gits database .. 

# GIT OBJECTS  
- Commits 
- Blobs(files) 
- Trees(Directories) 
- Tags