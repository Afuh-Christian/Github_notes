# 13 Splitting a Commit  5:05:00

- Let's try to split two commits that are unrealated ... 






<view log>






> git rebase -i <commitID>~1

- chose <edit>


- Now the head is poinint to the commit you wish to split ... 

> git reset --soft HEAD~1 

- You will see in the status 2 or more unstage changes ... 
- we stage the changes differently and make a commit for each ...

E.g .
M f1.txt 
?? f.txt 

# first stage f1 
> git add f1.txt 
> git commit -m "f1.txt added" 

# Next .... stage f.txt 
> git add f.txt
> git commit -m "f.txt added"


> git  rebase --continue 

Now wne we view the log , we see two new commits .... 



