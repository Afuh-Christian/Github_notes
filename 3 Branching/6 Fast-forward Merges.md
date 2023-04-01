# 6 Fast-forward Merges    2:16:07     

NB: when displaying all the list of commits  , we will use the (--graph) so that we should see how the branches are arranged .... 

> git log --oneline --all --graph


# Output
* 7e48292 (HEAD -> master) New stashed update
| * 75a49fe (bugfix) Deleted file1.txt in bugfix
| * 31af6cd Work done by new branch
|/
* 01322ec New Update


# the above represents a 3-way branching .... 
- because a commit was done on the master after the bugfix had already had it's own commit 















# We are dealing with Fast-forward in this section 
- We should delete the other branch there .. 

- Create a new branch and do some commits on it ... do not switch to master and do other commits on it too , cuz it will become 3-branch ....

- after creating the new branch , there should be no more committing to the master branch ... 

- after all that now .... 

> git log --oneline --all --graph 

# Output 
* a26a070 (bugfix) branch for fast-forward
* 7e48292 (HEAD -> master) New stashed update
* 01322ec New Update
* 8019df1 File2.txt Restored in working directory

# so now we have a linear path from bugfix to master ..


# To do the merging ... 

> git merge <branchname>
e.g 
> git merge bugfix 


# check the history now ... 

> git log --oneline --all --graph
# Output 
* a26a070 (HEAD -> master, bugfix) branch for fast-forward
* 7e48292 New stashed update
* 01322ec New Update

- Now both master and bugfix are pointing to the latest commit of the bugfix branch ... 

- Done .... 

# Now we can delete the bugfix branch normally since we have merged it .... 

> git branch -d  bugfix
































# How to disable a Fast-forward merge 
- this has a number of benefits 
     

- we'll create an switch to a new branch ... .

> git switch -C bufixA

- do some edits and commit them ... 

# let's merge bufixA to master using (no fast forward option )   ..... 

- first switch back to master 

> git switch master 

> git merge --no-ff bufixA

- with this  , we are telling git 
    - Event if fast forward(ff) is possible , 
    don't do it . 
    - create a merge commit that combines all the changes in the target branch (bugfixA ) and bring them to master ... 



# View results 
> git log --oneline --all --graph
# Output .....
*   84c77d5 (HEAD -> master) Merge branch 'bugfixA'
|\
| * c254dbc (bugfixA) Created file3.txt
|/
* a26a070 branch for fast-forward
* 7e48292 New stashed update



# Benefits of disabling ff merging ... 

- 





















# How to disable a Fast-forwar merge Globally .... 

> git config --global merge.ff false
or
> git config --global --add merge.ff false


# How to disable a Fast-forwar merge Locally .. in your current repository ... 

> git config  merge.ff false
or 
> git config --add  merge.ff false 























# NB ... always delete a branch after merging it ..

> git branch -d <branchname> 





