# To remove file from project .. 
> rm file2.txt

# check git status 
> git status 

- we see and error of a file deleted 

# files in staging area 
> git ls-files

- we still see the deleted file in the staging area 

# To stage the change ... 

> git add file2.txt 

- this will stage the change which is a deletion 

# Now when you check the files in the staging stage 
> git ls-files  

-  you now see that file2.txt is no longer available  

# check status .. 
> git status 

- Now error ... we see and update message "deleted: file1.txt"



# Now finally we commit the change ... 
> git commit -m "Removed unused code" 









# BETTER METHOD ... shorter ... 
-f = force 
> git rm -f file2.txt 
or 
> git rm -f *.txt 
> git rm -f . 

- git removes this file from the : 
    - working directory &
    - staging area











