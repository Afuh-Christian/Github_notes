# 2 Working with Branches  2:01:38

# Let's say we have a bug report  in the project ... to fix this bug ....  ........................................................................................................................

# - create a new branch called "bugfix"

> git branch bugfix 

# - to see the list of branches 

> git branch 
# output 
  bugfix
* master

- this (*) means we are currently on the master branch .. 

# another method to see the current branch we are working on ..... 

> git status 
# output 
On branch master 


# Now to fix this bug ...................................................................................................................................

# - change the current branch to bugfix ....

> git switch bugfix

# - How to rename a branch .... 

> git branch -m <oldname> <newname> 
eg . 
> git branch -m bugfix bugfix/signup-form 














# When we run a few new commits with this new branch , we now see explicitly that : 
- master branch is still pointing to the same old commit it was pointing to , about a number of commits before the new commits of the new branch .... 

- soon we will see how to make the head to point the master branch and make all the commits of the new branch be the commmits of the master branch ...


# When we switch between the different branches the project directory will not be thesame for both ... 
- so branching allows us to work on different code bases in isolation .... 

- And at some point we will merge them to bring them together .... 




# View all commits of all branches .... 

> git log --oneline --all 



















# delete a branch 

> git branch -d bugfix/signup-form 
# output 
- you get an error because you have not yet merged this branch with the master branch .... 
- git tries to prevent a person from accidentally deleting a branch ... 

# Force delete a branch 

> git branch -D <branchname>   








# shortcut to create and switch to a branch at thesame time ... 

> git switch -C <newbranchname>

-C = create