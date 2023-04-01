# 5 Reverting commits   4:38:29    .... 


# Option 2 .... We have pushed the commits to a remote repo an we want to undo 1 or more commits 
- reseting the head is not an option because we do not want drop the commits we have shared with others .... 




# We have to use the revert command .. .


# view the log ... .
* e76fa08 (HEAD -> master) added 2 to f2
* f116cd0 added 1 to f2
* 1cf679f Created f2
* 0df7271 Initial C

# To reverto the <e76fa08 commit>   ... 
> git revert  HEAD

# To revert an earlier commit e.g ..  <1cf679f commit>
> git revert  HEAD~2

# .......................We can specify a range ..

- Revert  the last 3 commits ... 
> git revert  HEAD~3..HEAD

- when we run this comman , git will revert each of this commits at a time ... 
- <VIEW LOG>
* 714c18e (HEAD -> master) Revert "Created f2"
* efc7ccb Revert "added 1 to f2"
* c07d752 Revert "added 2 to f2"
* e76fa08 added 2 to f2
* f116cd0 added 1 to f2
* 1cf679f Created f2
* 0df7271 Initial C


# Drawback ... 
- this is very noisy
- <It would be better to revert all those commits using a single commit ...> 
















# revert all those commits using a single commit
- reset head to it's normal position to get rid of the revert commits .... 

> git reset --hard e76fa08
or
> git reset --hard HEAD~3

- <view log > 
* e76fa08 (HEAD -> master) added 2 to f2
* f116cd0 added 1 to f2
* 1cf679f Created f2
* 0df7271 Initial C

- we see that all the reverted commits have been removed ... 



# Now the command to revert the last 3 commit .... 

> git revert --no-commit HEAD~3..HEAD
OR
> git revert --no-commit HEAD~3..
 
- <opiton   --no-commit : git will add the required changes in the staging area>
    - so for every commit  that we are going to revert , git will figure out the changes that needs to be or not ..
    - then it will apply those changes in the <staging area>   


# CHRISTIAN@CLaptop MINGW64 /e/Saved Files/Courses/GITHUB/GITHUB/5 Rewriting History/Mercury (master|REVERTING)

# - If we wish to get out of this reverting state .. 

> git revert --abort 

# - If we wish to continue in the state and do the changes ..

> git revert --continue

- we will be asked to give the commit message of the one commit that will represent all those reverts ..... 
- Let's give a unique name ... 

- <view log>
* 7b65da3 (HEAD -> master) Revert numbers file
* e76fa08 added 2 to f2
* f116cd0 added 1 to f2
* 1cf679f Created f2
* 0df7271 Initial C


# Now we have a single commit that represents all the reverts .... so we can push this to the origin and share with others ..... 
