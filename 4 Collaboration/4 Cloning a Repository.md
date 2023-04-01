# 4 Cloning a Repository   3:23:45              .... 

- Now there's a repo in the cloud ... 
- Every team member should clone this repo (they should take a copy of this repo an put on their machine ..)
- Locally , they will work on that repository and when they are ready to share their changes , they will <push> their commits to this central repository



# To clone the Mars repository .... 3:24:09 

- https://github.com/Afuh-Christian/Mars


> git clone https://github.com/Afuh-Christian/Mars.git


NB .. here the default main branch is called "main"


# We can view all the commits in this repository .... 

> git log --oneline --all --graph
# ouput 
* 6bbd24a (HEAD -> main, origin/main, origin/HEAD) Initial commit



-  origin/main = where is the main(master) branch in our origin repository 
    - this is called a remote tracking branch 
    - It's a branch, but not the once we are familiar with .
    - so we cannot <checkout> , <commit> , <switch> to this branch
- origin/HEAD = tells us where is the HEAD pointer in our origin repository






# How to view the list of remote repositories .... 

> git remote 
# ouput 
origin



- remote repository 
    - this is a repo that is not on our machine
    - Or it's not in the current directory
- currenly , we have a single remote repo , that is our origin repo. 


# To see more details about the repote repository .... 

> git remote -v 
# output 
origin  https://github.com/Afuh-Christian/Mars.git (fetch)
origin  https://github.com/Afuh-Christian/Mars.git (push)


-v = verbose 


- so this means "origin" is referencing the  https://github.com/Afuh-Christian/Mars.git repo

