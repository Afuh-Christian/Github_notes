# 13 squash Merging   .....  2:44:09 .... 
         
         master
          |
C <- C <- C  
      \
       \
        B1 <- B2 
               |
             bugfix

- Here we have a bugfix branch with 2 commits ... 
    - B1 
    - B2
- Let's say we are done and we do a merge




                master
                  |
C <- C <- C <---- M
      \          /
       \        /
        B1 <- B2 
               |
             bugfix

- Now this commits B2 and B2 are part of the history of master
- what if this commits are not good commits 
    - No definite logical change 
- we do not want this commit to polute the history of our master branch ... 

# Process ... 

- we undo the merge 

         master
          |
C <- C <- C  
      \
       \
        B1 <- B2 
               |
             bugfix

- we create a new commit  that combines all the changes in the  bugfix branch .. so we have a single logical chainset that represents all the changes in the bugfix branch

 (B1+B2)

- Now we apply this commit on master 

                            master 
                               |
C <- C <- C <---------------(B1+B2)
      \
       \
        B1 <- B2 
               |
             bugfix

- this is squash merging .. 

# NB ... this new commit is not a merge commit because 
- it doesn't have two parents ..
- it doesn't have a reference to B2
- It's just a regular commit that we have added ontop of master 


# We can delete the bugfix branch after this ... 


                            master 
                               |
C <- C <- C <---------------(B1+B2)



# this approach should be used with small shortlived branches with bad history , bug fixes or features that you can implement in a day or a few hours ..











































# Now let's see this with an example  ..... 

# bugfixB branch
- create new branch 

> git switch -C bugfixB

- we'll make 2 commits , in each we'll update one file .

-       1ST COMMIT 

> echo bugfixB >>  demo2.txt

- add and commit the  changes ..

> git commit -am "Update demo2.txt"

-       2ND COMMIT  

> echo bugfixB2 second >>  demo.txt

- add and commit the  changes ..

> git commit -am "Update demo.txt"


# chech history 
> git log --oneline --all --graph
* b79442f (HEAD -> bugfixB) Update demo.txt
* 7235179 Update demo2.txt
* af1c61a (master) Revert "Merge branch 'ptestbranch' to master"

# from here we could do a ff merge ... but we want to have a case of a 3-way first .... 

# master branch

> git switch master 

# we can proceed with the merging ... 

> git merge --squash bugfixB     
# output 
Updating af1c61a..b79442f     
Fast-forward
Squash commit -- not updating HEAD
 demo.txt  | 1 +      
 demo2.txt | 1 +
 2 files changed, 2 insertions(+)


- git created a new commit called a "Squash commit" 
which combined the changes accross demo.txt and demo2.txt

# NB ... we do not have a commit yet ...all the changes are in the staging area 

> git status -s 
# Output 
M  demo.txt
M  demo2.txt

- Now we have to commit them ... 

> git commit -m "Fix the bug on BugfixB"




# check the history 

* 7cabcb9 (HEAD -> master) Fixed the bug on BugfixB
| * b79442f (bugfixB) Update demo.txt
| * 7235179 Update demo2.txt
|/
* af1c61a Revert "Merge branch 'ptestbranch' to master"



# Done ...

# Now we delete the bugfix branch and end up with a simple linear history .... 

we delete with this command because the bugfixB branch is not exactly merged to master

> git branch -D bugfixB  







# If we end up with a conflict , we will use thesame method we did for resolving it ... 





# NB ... 

--no-ff   and   --squash cannot be used together 
