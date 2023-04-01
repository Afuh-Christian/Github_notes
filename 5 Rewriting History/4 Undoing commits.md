# 4 Undoing commits     4:33:34        .... 

- Let's try to undo the last commit ... of a project. ... 

# we have tow options ... 
- If we have already <pushed this commit to a remote repo> , chances are other people have based their work ontop of this commit .. 
    - So we shouldn't remove this commit 
- We should use the <revert commit> , this will <create a new commit that will undo all the changes in this commit >
> git revert  HEAD

























# Option 1 .... we haven't pushed the commit to a repo online ..

- We can use the <reset command> to remove the commit from history 

> git reset  --hard <target position for head pointer>
> git reset  --hard HEAD~1


# Let's check the --hard , --soft , --mixed ............

- Before ... 

      B                     B                 B  <----- HEAD
  working dir         staging area            A

# --soft 
> git reset --soft HEAD~1

      B                     B                 B (deleted)
  working dir         staging area            A  <----- HEAD


# --mixed 
> git reset --mixed HEAD~1

      B                     A                 B  (deleted)
  working dir         staging area            A  <----- HEAD



  
# --hard 
> git reset --hard HEAD~1

      A                     A                 B  (deleted)
  working dir         staging area            A  <----- HEAD

# end .....................................................



 










# .... Let's use the --soft and see how to go around it..... 

> git reset  --soft HEAD~1

# if we check the status we will have staged changes from the previous commit we just removed ... ready to be commited back to the old commit we just removed 

#  To unstaged the staged files in  the staging area 

- Now HEAD = HEAD~1   ... after runing the reset command ... 
- So we reset the HEAD with the HEAD  using <mixed> so that that staging area will be updated ... 

>  git reset --mixed HEAD 

# Now if we check the status  , we will see untracked changes from the working directory .... ready to be staged and commited to the old commit we just removed .... 

# To remove those UNSTAGED FILES in the working directory ... 

- we reset the HEAD  with the HEAD using <hard> so that the working directory will be updated to be same as that of current latest commit ... 

> git reset --hard HEAD




# NB ... 
- <compare staging area vs commit> 
    - > git diff --cached 


- <compare working dir vs staging area> 
    - > git diff 


- <See changes in a commit > 
    - >git show <COMMITid>