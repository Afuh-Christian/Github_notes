# 11 Re-Ordering Commits   5:00:08 .... 

- Let's try changing the order of commits ... (changing the position of commits .... )

<View log> 
* 44825bb (HEAD -> master) 1st
* 638a97d 2nd
* 59f042a added 2 to File2
* 44bbe49 added 1 to f2
* 0df7271 Initial C


# let's swap commits with messages "1st" and "2nd"

- grab the "initial C" so we can see all the commits ... 

> git rebase -i 0df7271

- in this file containig all the commits ... we manually place the commits in the order we want using the commands provided 
- <alt + down> or <alt + up>  to send a commit up or down ... 
- <close the git-rebase-todo> 

- <done .... > 

# if there's a conflict error ... resolve it ...and continue ... 

