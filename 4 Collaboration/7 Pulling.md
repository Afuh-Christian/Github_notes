# 7 Pulling         3:31:13         

- So to bring in the changes in the remote repo into our local repo , mostly we do a 
    - <fetch>  +   <merge>
- we have a command that combines both.... 

- <pull> = <fetch> + <merge> 



     Local                  |     remote(repo in github cloud) 
                            |                                  
                            |                                  
     master                 |              master              
        |                   |                |                 
        V                   |                V                 
        A                   |                A
        ^                   |                
        |                   |                  
     orgin/master           |  
                            |                                     

Now .... 
- Let's say we add a commit in our local repo B  and Add add a commit in the remote repo C 


     Local                  |     remote(repo in github cloud) 
                            |                                  
                            |                                  
           master           |                            
             |              |          master                 
             V              |            |                     
        A <- B              |            V
        ^                   |       A <- C          
        |                   |                  
     orgin/master           |  
                            | 

- When we run <git pull> , git will download c and put to our 
local git repo


     local repo ..


        master
         |
    A <- B 
     \
      C 
      |
    origin/main

- Now it's diverged ... git will perform a <three-way-merge> .. 

     local repo ..

           master
              |
    A <- B <- M 
     \       / 
      \     /
       \   /
         C
         |
    origin/main

- Lot's of people don't like this method  because they 
    - Polute the history 


# Alternatively ,,, we can use rebasing ... 

- git well rebase the master branch ontop of origin/master
<git pull --rebase>
- current base of master branch is A .... rebase will change it to C


local  

        master
          |
A <- C <- B 















# Example .... 
# - create a new commit ... in the remote repo .... 

- edit the readme file    
- commit the changes ...

# creeate another commit in the master .... 

> echo hello  > file1.txt
> git add . 
> git commit -m "Add file1.txt"






# To download new commit in git repo and perform a 3 way merge . 

> git pull 

# view the log .. 
*   6591851 (HEAD -> main) Merge branch 'main' of https://github.com/Afuh-Christian/Mars
|\
| * d9fe388 (origin/main, origin/HEAD) PUll commit
* | 7c9b6d3 Add file1.txt

- <You notice the 3-way merge has already been performed ...> 

















# let's undo this and try  another method .... 

> git reset --hard HEAD~1

# view history .. 
* 7c9b6d3 (HEAD -> main) Add file1.txt
| * d9fe388 (origin/main, origin/HEAD) PUll commit
|/
* 8deacee New Mars commit



















# Alternatively ... to download new commit to local git repo and perform rebasing to linear history and then ff-merge ... 

> git pull --rebase 


# view the log ... 
* 84b270c (HEAD -> main) Add file1.txt
* d9fe388 (origin/main, origin/HEAD) PUll commit
* 8deacee New Mars commit
* 6bbd24a Initial commit


<Done ......>

