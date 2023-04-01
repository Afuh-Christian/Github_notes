# 6 Recovering Lost Commits     4:41:59     .. 

- We we revert  to a previuos commit and try to recover the commit we just removed .... 

- <view log>
> git log --oneline --all --graph 
* 7b65da3 (HEAD -> master) Revert numbers file
* e76fa08 added 2 to f2
* f116cd0 added 1 to f2
* 1cf679f Created f2
* 0df7271 Initial C

# ..... Remove the last 3 commits .... 

> git reset  --hard HEAD~3

<view log > 
* 1cf679f (HEAD -> master) Created f2
* 0df7271 Initial C


# .... Recover all those commits ...
- All the commits are still in the repo even if we do not  see them  when looking at the history .... 
- <git keeps all those removed commits for a while and if they are not used then , it will "Garbage "collect "them >
- we will use this command to recover the lost commits ... 

# .....git reflog......
- Git will show how the <head pointer has moved in our history>
<reflog = a log of how a reference was moved in our history >

> git reflog

# output ... 
1cf679f (HEAD -> master) HEAD@{0}: reset: moving to HEAD~3
7b65da3 HEAD@{1}: commit: Revert numbers file
e76fa08 HEAD@{2}: reset: moving to e76fa08
e76fa08 HEAD@{3}: reset: moving to e76fa08
714c18e HEAD@{4}: revert: Revert "Created f2"
efc7ccb HEAD@{5}: revert: Revert "added 1 to f2"
c07d752 HEAD@{6}: revert: Revert "added 2 to f2"
e76fa08 HEAD@{7}: reset: moving to HEAD
e76fa08 HEAD@{8}: reset: moving to HEAD
e76fa08 HEAD@{9}: reset: moving to HEAD~1
1b672b4 HEAD@{10}: commit: added letter to f2
e76fa08 HEAD@{11}: commit: added 2 to f2
f116cd0 HEAD@{12}: commit: added 1 to f2
1cf679f (HEAD -> master) HEAD@{13}: commit: Created f2
0df7271 HEAD@{14}: commit (initial): Initial C


<Every entry has a unique identifier e.g HEAD@{0}>
<We can reset all our commits by using the commit with HEAD@{1}>

> git reset --hard HEAD@{1}

<view log .. all our commits are back ....>
* 7b65da3 (HEAD -> master) Revert numbers file
* e76fa08 added 2 to f2
* f116cd0 added 1 to f2
* 1cf679f Created f2
* 0df7271 Initial C

# ............





















# Now we Can use the <reflog to see how all other pointers have moved in history.>
- To see the history of a <brancn> e.g ... feature ... 

> git reflog show <branchname>