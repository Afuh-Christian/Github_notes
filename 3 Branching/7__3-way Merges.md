# 3-way Merges.    2:23:02 

- create a new branch called "feature" 

> git switch -C featureA

- when you view the history , you see that both the 
featureA and master are currently pointing to thesame branch ... 

# How the feature and master branch can diverge ... 

- Let's make a change to both the featureA and master branch respectively .... 

# featureA
- create a new file and add text to it , then add & commit the change

> echo newfile > file4.txt 
> git add . 
> git commit -m "Build the change password form " 


- Now when we check the history , we see that the featueA branch is one commit ahead of the master branch ... 


# master 
- create a new change and commit it . 
> echo file3.txt >> file3.txt 
> git add file3.txt 
> git commit  -m "Made the change that caused the diverged branch" 

- Now this new master branch will be diverged into another direction because the new commit done here is not known by the feature branch 


             master
               |
C <- C <- C <- C
           \
            C 
            |
        featureA 


- Now we successfully have a 3-way branch


# Now check the history .... 

> git log --oneline --all --graph
# Outpuy ..
* c672015 (HEAD -> master) New update that caused diverted branch
| * 8d66700 (featureA) Build the change password form
|/
*   84c77d5 Merge branch 'bugfixA'




# Now to merge .... 

> git merge featureA



# then commit ..... 

> git commit 






















# view the history .... 

> git log --oneline --all --graph 
# output 
*   b7deef1 (HEAD -> master) Merge branch 'featureA' to master
|\
| * 8d66700 (featureA) Build the change password form
* | c672015 New update that caused diverted branch
|/
*   84c77d5 Merge branch 'bugfixA'
  