# 15 Cherry Picking   .....    2:57:30

- Picking commit a commit from another branch into master ...

       master
          |
C <- B <- L  
      \
       \
        F1 <- F2 
               |
             feature

- Let's say F1 has some interesting changes we want in master , but we are not ready to merge our feature branch with master 
- this is where we use "CHERRY PICKING" ... 
- so we can cherry pick F1 commit and apply to master .. 


            master
               |
C <- B <- L <- F1
      \
       \
        F1 <- F2 
               |
             feature








# Example how we can do this ... 

> git log --oneline --all --graph
# output .... we currenly have this .
* 2fe9758 (featureB) Update demo m
| * 26ffdc8 (HEAD -> master) Update demo m
|/
* febe2be featue upate


- we want the 2fe9758 commit of featureB in mastar without merging ..

# master branch 
> git cherry-pick 2fe9758

- we have  a conclict 

> git mergetool 
- choose the remote  since it's foriegn and is of  the feature branch ....

> git status -s
M  demo.txt


> git commit 


# View history ... 
- master has moved forward , and now we have the new commit from our cherry branch ..


