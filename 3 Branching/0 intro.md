# BRANCHING .... 

- Use branches - to diverse from the main line of development and work on something else in isolation
- Compare branches
- Merge branches 
    - 3 way merging 
    - fast forwarding
    - squash merging 
    - Re-basing
- Resolving merge conflicts
- Undo a faulty merge 
- Essential tools (stashing , cherry picking)



# what is a branch  1:57:00
- a separate isolated workspace
- main workspace - master 
    - annother workspace - feature
        - we work on this separately 
        - there could be bugs 
        - we test the code .. 
        - if everything is ok 
        - we bring the workspace into the master in a process called "MERGING"
- branching allows us to work on different work items (eg feature) without messing up with the main line of work (master)
- We do this to keep the master as stable as posible so it can be deployed anytime ... 
- anyone joining the team will start off on a clean code base (master)















# NB ... if you have a detached HEAD   like    (HEAD , master) 

- run  the command 

> git checkout master 

- you now get (HEAD -> master)  , means it has be reatached to the master branch ... 





# Git branching is different from others ... 1:59:20
- Here a branch is a pointer to the last commit 
- when a new branch (feature) is created , git create a new branch that also points to the latest branch 
    - This pointer is just a tiny file that contains a 40 byte commit ID , 
        - that's why creating a branch in  git is very fast
    - When new commits are being created , the feature branch keeps moving to the latest , but the  master branch stays put . 
    - so git knows the latest code in each branch


# - How does git knows which branch you're currently working on ...

- Using a special pointer called "HEAD" 
    - this pointer is also another tiny file that contains the name of the branch 
    - when you switch to a different branch , git moves the "HEAD" pointer to point to the new current branch ..
    - so it updates the tiny files and writes the name of the target branch ..
    this is how git tracks what branch we are current working on ..... 
  



