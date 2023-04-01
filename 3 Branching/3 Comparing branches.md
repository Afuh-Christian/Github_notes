# 3 Comparing branches 2:06:50

- Sometime we need to know the new branches are diverging from master 
- we need to compare the branches to master ... 

# How to compare a branch with master .................................................................................................... ..................................................................................................... 

# -Command to Show all the commits that are in bugfix that are not in master  

> git log master..bugfix

# - To see the actual changes ... 

> git diff master..bugfix

OR .... since we are currently in the master branch .. 

> git diff bugfix

# to see the changes in short form ....  

> git diff --name-status master..bugfix
> git diff --name-only master..bugfix


























# Once we merge bugfix to the master .... 
changes in bugfix changes will be updated and modified ....














