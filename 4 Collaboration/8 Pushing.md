# 8 Pushing         3:35:09 

# view the log ... 
* 84b270c (HEAD -> main) Add file1.txt
* d9fe388 (origin/main, origin/HEAD) PUll commit
* 8deacee New Mars commit
* 6bbd24a Initial commit 


local                |                      remote
                     |       
        master       |              master
          |          |                 |    
A <- B <- C          |            A <- B     
     |
    origin/master 


# From here , the master branch is ahead of origin/master by one commit .... 
- this is because the remote repo does not know about the other commit we did locally ... <Add file1.txt commit ..> 
- so we need to send this new command to origin (remote repo) 
- Using the <push> 

- when we run  <git push> 
    - commit C adds to remote repo , master pointer now points to it 
    - origin/master now also points to C in local repo too ...


local                |                      remote
                     |       
        master       |              master
          |          |                 | 
A <- B <- C          |            A <- B
          |
        origin/master 








# Example .... 

> git push <remoterepo> <branch-we-want-to-puch> 
e.g 
> git push origin master
or
> git push origin main
or 
> git push 





# view log now ...
* 84b270c (HEAD -> main, origin/main, origin/HEAD) Add file1.txt
* d9fe388 PUll commit
* 8deacee New Mars commit
* 6bbd24a Initial commit


# <Now everything is as it should be ... >



# NB ... sometimes your commit may get rejected .... 

- A and B are working on the same repo .... 
- A is ready to push his ... 
- If B has already pushed his commits already  , A's commits will be rejected because the version A is trying to add to is not thesame as before because B has already edited ... 

# so 
- A should <pull> all  the new commits to his local repo and merge before <pushing> his

# an alternative is to use 

> git push -f   

- this command will delete all other new commits and replace with A's commits ...