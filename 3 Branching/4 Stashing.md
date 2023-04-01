# 4 Stashing     2:08:42     ..........     

- When we switch from one branch to another .. 
- git restores the working directory with the copy of the last commit of the  target branch 

# So 
- local changes in the working directory that we haven't commited yet , these changes would get lost
- In this situations , git does not allow  us to switch branches ... 

# Make a change in file1.txt 

> echo newtextcahnge >> file1.txt 

# Try to switch branch new ... 

> git branch bugfix  
# output
error: Your local changes to the following files would be overwritten by checkout:
        file1.txt
Please commit your changes or stash them before you switch branches.
Aborting

# we don't want to commit them cause are not done ... 
# so we will stash them 











# Stashing 
 - storing the file somewhere in the git repository , will not be part of our history .

# Stashing the file1.txt ...

> git stash push -m "New file1.txt update in master" 

# ouput 
Saved working directory and index state On master: New file1.txt update in master

# .....
- the message here tells us what these changes are all about ....


# NB ... by defualt , new untrackted files are not included in the stash .... 
- If we do another change ... we still have to add it to the stash using another command. 

> git stash push --all -m "My new stash"
OR
> git stash push -a -m "My new stash"
OR
> git stash push -am "My new stash"

# Output 
Saved working directory and index state On master: My new stash


# To list all stashes..

> git stash list

# Output
stash@{0}: On master: My new stash
stash@{1}: On master: New file1.txt update in master

- Each stash has a unique identifier 
























# Now we can safely switch to a new branch since all the uncommitted changes have been added to a stash in the master(current branch) 

> git switch  bugfix 

- let's go back to the master branch ... else we won't be able to operate on the staches .... because they were form on that branch ..... 


> git switch master 











# To see a particular stash and what modifications were made before it needed to be stashed  ..

- use the stash identifier .. 


> git stash show stash@{1} 
Or 
> git stash show 1 












# Now we can apply(bring) to the working directory ..
- To apply a particular stash ...eg stash@{1}

> git stash apply 1  
# Output 
You get a status respond for the master branch talking of an unstagged edit ..





# To delete a stash .... 

> git stash drop <stashId>
e.g
> git stash drop 1


# To delete all stashes

> git stash clear






