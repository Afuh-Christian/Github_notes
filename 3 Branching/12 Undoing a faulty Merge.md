# 12 Undoing a faulty Merge    ....   2:38:41   

- Sometimes we do a merge and then we find out that our code does not get compiled (or the app doesn't work).
- This happens if we do not combine the changes properly 
- In scenarios like this , we need to undo the merge and then re-merge .





# Let's assume the last merge we did was a faulty merge an we want to undo it .... 

# view all commits ... 

> git log --oneline --all --graph   

# Output 
*   61f88cb (HEAD -> master) Merge branch 'ptestbranch' to master
|\
| * e142172 (ptestbranch) p4test
* | be4030c p4test
|/
*   3af4314 Merge branch 'ptestbranch' to master


# We have two options ... 











# method_1 ...............NB : use this method only if you haven't shared your history with others .............................................................................................................................................................................
- remove the latest commit 
- we have to be carefull with this method because 
    - as we remove commit , we are rewriting history 
    - rewriting history is totally fine if this history is just local in our repository 
    - but if we  have shared our commits with other team members ( pushed the commits to a remote repository ) , then we shouldn't rewrite our history .


              master
                |
C <- C <--------C
      \        /
       \      /
        C <- C

# we will use the reset command to move the master pointer to the last commit before we started the merge. 

    HEAD
     |
   master
     |
C <- C <--------C
      \        /
       \      /
        C <- C

# NB.. copy the id of the lastest commit and save somewhere first ... 

61f88cb



> git reset --hard HEAD~1

HEAD~1   =  one commit before the last commit .. 


# reseting ... when resetion the head pointer , we have 3 options ... 
- soft  
    - > git reset --soft HEAD~1
    - staging area and working directory are not affected 
- mixed 
    - defualt     
    - > git reset --mixed HEAD~1
    - puts the new snapshot in the staging area
- hard
    - > git reset --hard HEAD~1
    - puts the new snapshot in the staging area and working directory 


# Now view the commits 

> git log --oneline --all --graph
# Output 
* be4030c (HEAD -> master) p4test
| * e142172 (ptestbranch) p4test
|/
*   3af4314 Merge branch 'ptestbranch' to master


# Now we are at the previous state ... from here we can abort if we do not wish to continue .. 

# We can still recover the merged state , by using the id we copied from above and save , because that particaular commit is still in our repository ... 

# we can undo what we just did by using the id we saved 

> git reset --hard 61f88cb

# chech the commits if it worked .. 

> git log --oneline --all --graph 
# output 
*   61f88cb (HEAD -> master) Merge branch 'ptestbranch' to master
|\
| * e142172 (ptestbranch) p4test
* | be4030c p4test
|/
*   3af4314 Merge branch 'ptestbranch' to master









































# method_2 .................... NB : use this method if you have shared your history with others ...................................................................................................................................................................................................................................2:43:01
- We revert the last commit ..(we will create a new commit that will cancel all the changes in this commit )

> git revert HEAD
# Output 
error: commit 61f88cbe8fd1117e57457d11eefd287243092ec7 is a merge but no -m option was given.
fatal: revert failed


# explainig the error 
- a merge commit has two parents 
    - parent1 
    - parent2 

  parent1      master
     |          |      
C <- C <--------C
      \        /  
       \      /
        C <- C
             | 
           parent2 

- we want to revert to the last commit of the master branch . 
- so we have to explicitly tell git we wish to revert to parent1 (last commit on master branch before we started the merge ... )
- parent1 is the first parent of the merge commit
    - because our merge commit is on the master branch 
    - so the first parent should also be on the master branch


> git revert -m 1 <targetcommit>
e.g 
> git revert -m 1 HEAD

1 = first parent 


# chech history ... 

> git log --oneline --all --graph
# output 
* af1c61a (HEAD -> master) Revert "Merge branch 'ptestbranch' to master"
*   61f88cb Merge branch 'ptestbranch' to master
|\
| * e142172 (ptestbranch) p4test
* | be4030c p4test
|/
*   3af4314 Merge branch 'ptestbranch' to master

 
# NB ... here no commit is bein deleted ... we still have the last merge commit , but now the latest commit was created with message "Revert..."