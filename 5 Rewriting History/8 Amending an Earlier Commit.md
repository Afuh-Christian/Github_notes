# 8 Amending an Earlier Commit  4:48:13 .... 

- Now how we can Edit an Earlier commit (any other commit appart from the latest...) .... 




# view log ... .
* 82f1f91 (HEAD -> master) Edited map
* 64b622a Render cafes on the map. to use
* 7b65da3 Revert numbers file
* e76fa08 added 2 to f2
* f116cd0 added 1 to f2
* 1cf679f Created f2
* 0df7271 Initial C



# let's edit .... <* f116cd0 added 1 to f2>
- we will use it's parent which is <c=   *1cf679f Created f2>
- we will use <Interactive rebasing> to do this ... 

> git rebase -i 1cf679f

- we get a series of  intructions involving the rebase action ... 
- We can e
    - <pick> , <edit> , <drop> etc... 
- we'll chose <edit> for just one commit ... the commit we want to edit .... NB we can also edit multiple commits ....
- When we close the <git-rebase-todo> file .. the rebase-i proces starts .... 

- <CHRISTIAN@CLaptop MINGW64 /e/Saved Files/Courses/GITHUB/GITHUB/5 Rewriting History/Mercury (master|REBASE 1/5)>

> echo christian >> map.txt
> git add . 
> git commit --amend 

<View log to see what happend ...>

> git rebase --continue

# we can abort if we made errors 

> git rebase --abort  



# NB .. maintaing the commit name .... 

# Nb ... the changes that was done in an earlier commit is carried out throughout the history .....







# NB .. When we do this ... 
- a new commit is being created ... 
- all the other commits after this commits are also recreated ... 

# Rebasing rewrites history and should only be used when you haven't share you're work with others .... 


