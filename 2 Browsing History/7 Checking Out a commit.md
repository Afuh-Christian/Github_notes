# 7 Checking Out a commit 1:32:00 
- sometimes , we will want to see a complete snapshot of our project at a particular point in time ... 

# In this situation 
- we will checkout a given commit 
- this will restore our working directory to the snapshot stored in that commit 
- So our working directory will look exactly like an earlier point in time .


# Restore our working directory to an old commit(version)  .....  

- show list of commits 
> git lg 
- chose a particular commit and replace the working directory with it .... 

> git checkout 3d7addc

# NB - we get a warning "You are in 'detached HEAD' state 

# Explanation .... 
 - Each new commit points to the old commits 
 - All the commits we have created so far are part of the MASTER (the main line of work) 
 - Every git repo has a defualt branch called MASTER
 - Git represents branches using a pointer
 - MASTER is pointing to the last commit created 
 - As new commits are created , MASTER moves foward to point to that new commit 
 - since we can have multiple branches , git needs to know which branch we a currently working on . 
    - Git uses another special pointer called 'HEAD'
    - 'HEAD' points to the current branch we are working on , in this case 'MASTER'
    - We have seen this before .... (HEAD -> master) when we run the "git log --oneline" command to display all commits 
    - As we create new commits ... (HEAD -> master)  will move foward

# the problem ... 
- when we checkout a particular commit 
> git checkout 3d7addc 
- the 'HEAD' pointer will move and point to that commit ('HEAD' is supposed to point to branch not a commit)
- we call this a "DETACHED HEAD"
- At this point ,we can't create any new commit because it will now point to the 3d7addc commit , which will not be reachable

# Now if you run the 
> git log --oneline

# output ... not correct cuz (HEAD) now point to commit
3d7addc (HEAD) fix the bug that prevented the users from signing up
892f5af new file created
55f55e9 Initial commit

# we are able to see just some commits 

# To see all the commits 

> git log --oneline --all

# output

# 1950f41 (master) Added file1 again
6396b1a Deleted file1.txt
f38f0f0 Removed the bin directory that was accidentally committed
0ab0a98 Add gitignore
04e7d86 Remove unused code
# 3d7addc (HEAD) fix the bug that prevented the users from signing up
892f5af new file created
55f55e9 Initial commit













# To attache the HEAD  back to the master branch 

> git checkout master

- Now we can create new commits ... 
- let's view the commit's to see if problem is fixed , 
> git log --oneline 
# output 
# 1950f41 (HEAD -> master) Added file1 again
6396b1a Deleted file1.txt
f38f0f0 Removed the bin directory that was accidentally committed
0ab0a98 Add gitignore
04e7d86 Remove unused code
3d7addc fix the bug that prevented the users from signing up
892f5af new file created
55f55e9 Initial commit



