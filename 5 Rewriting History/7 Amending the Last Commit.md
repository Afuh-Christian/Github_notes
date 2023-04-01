# 7 Amending the Last Commit       4:44:35         .... 

- How we can modify the last commit ... 

 > echo cafes > map.txt
 > git add > 
 > git commit  -m "Render cafes on the map "


# let's say we wanted to render "Blue cafes" rather

> git Blue cafes >> map.txt 
> git add .
# to ammend this to the latest commit .... 

> git commit --amend -m "<new message to replace the old >"
Or .... resuse the old message
> git commit --amend 



# View log to see if it was done ... 
* 64b622a (HEAD -> master) Render cafes on the map. to use
* 7b65da3 Revert numbers file
* e76fa08 added 2 to f2
* f116cd0 added 1 to f2
* 1cf679f Created f2
* 0df7271 Initial C


















# .... Lets say we want to remove a file ...... 

- create a commit that adds a file ... 
- let's try to remove this file ... 

> echo h > h1.txt
> echo hello >> map.txt
> git add .  
> git commit -m "Edited map"


# Now let's remove the h1.txt file ... that was added in this commit ... 

> git reset  --mixed  HEAD~1
- remove untracked files from staging area .... 
> git clean  -fd
> git add .  
> git commit -m "Edited map"





<View log ... > 
* 82f1f91 (HEAD -> master) Edited map
* 64b622a Render cafes on the map. to use
* 7b65da3 Revert numbers file
* e76fa08 added 2 to f2
* f116cd0 added 1 to f2
* 1cf679f Created f2
* 0df7271 Initial C


- <Check to see if h1.txt is in HEAD> 
> git show HEAD



