# 5 Merging   ......    2:12:48 

- This is all about bringing changes from one branch to another ..

# There are two types of merging in git .. 
- Fast-forward merging 
- 3-way merging



# Fast-forwad merging
- when there is a linear pathway from the (master branch) -> (bugfix branch)

- git just has to bring the master branch up to the bugfix(new branch) branch so that both of them will point to the latest commit in the bugfix(new branch) branch

        master    
          |         
C <- C <- C <- C <- C
                    |
                  bugfix 

- to merge them  , we rename the bugfix -> master 

                 master
                    |
C <- C <- C <- C <- C

# 3-Way merge
- when there are 2 or more divertions from the master branch ... (no linear path ..) 
- when the master is in one branch
- new branch is on another divertion 

             master
               |
C <- C <- C <- C
           \
            C <- C
                 |
               bugfix 

- so we have a Commit that doesn't exist in the bugfix branch (the one master points to currently)
- if we use the method of renaming the bugfix -> master , we will loose the latest commit of the master branch .... 

- So in this situation , when we run a merge here , git creates a new commit that combines the changes from the  current master branch and the bugfix branch  

                   master
                     |
C <- C <- C <- C <-- C  
           \        /
            \      /
             C <- C
                
- This is called a two way merge because it depends on 3 things .. 
- Common ancestor of the branches (A) : contains before code 
- Tips of the branches (T) : contains the after code 


          A    T    master(merge commit)
          |    |     | 
C <- C <- C <- C <-- C  
           \        /
            \      /
             C <- C
                  |
                  T

- so git at 3 different snapshots , the before snapshots, and after snapshots ... 
    - based on these it will figure out how it should combine these changes to form the  "MERGE COMMIT"







# Summary ...
 
# MERGES ....
- Fast-forward (if branches have not diverged) 
- 3-way (if branches have diverged)







