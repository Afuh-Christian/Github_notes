# 10 Rewording commit Messages      4:58:26       




- Correcting spellings in commit messages  .... 
- We can reword multiple commits .... 



<view log ...> 
* 8a0f6f8 (HEAD -> master) added 2 to f2
* 44bbe49 added 1 to f2
* 0df7271 Initial C


# change the name of the HEAD commit .... 

> git rebase -i HEAD~1 

- choose the <reword> option

- Git will go throug all the commits we want to <reword>


<View log> 
* 59f042a (HEAD -> master) added 2 to File2
* 44bbe49 added 1 to f2
* 0df7271 Initial C

<done..>

# NB this created a new commit ....  do this when you haven't shared you're project with anyone ... 
