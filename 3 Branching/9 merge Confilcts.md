# 9 merge Confilcts  2:27:26

- this happen when the same line of code has been changed in different ways in two branches

- Or if a file is changed in one branch and is deleted in another branch .

- if the same file is added twice in two different branches be both having different content ...


# In cases like  this , git can't figure out how to merge these kind of changes .... 

- It will stop the merge process .. 
- we need to tell git how we wish to proceed

# Add a new branch .... democopy 
> git switch -C demoCopy 
> echo democopy > demo.txt 
> git add . 
> git commit -m "Updated the demo.txt" 


# Do this same change in the master but with differnt content of demo.txt .... commit with same commit message
> git swtich master 
> echo democopymaster > demo.txt 
> git add . 
> git commit -m "Updated the demo.txt" 


# Now try to merge ... 

>  git merge demoCopy
# ouput ....
Auto-merging demo.txt
CONFLICT (add/add): Merge conflict in demo.txt
Automatic merge failed; fix conflicts and then commit the result.


# check status 

> git status -s
AA demo.txt

# Nb ... AA means both branches applied additions...
# NB ... the more diversed your app is , the more merge conficts you'll have ..... 


















# How to fix this conflict .... 

- view the file causing the problems .... 

> code demo.txt

<<<<<<< HEAD
democopymaster
=======
democopy
>>>>>>> demoCopy



# METHOD 1 ... 

- manually remove 
    - <<<<<<< HEAD
    - =======        : divider 
    - >>>>>>> demoCopy

# result 
democopymaster
democopy

- now add the demo.txt  
# CHRISTIAN@CLaptop MINGW64 /e/Saved Files/Courses/GITHUB/GITHUB/3 Branching/Moon (master|MERGING)

> git add demo.txt

> git commit


