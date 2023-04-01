# 6 Fetching           3:26:39            


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

- Local repo is not connected to remote repo
- if there's a new commit in the remote repo , the local repo will not be aware of that . 

- we have to use the <git fetch> command to download this new commit 
- git will download this new commit and move the origin/master forward .(orgin/master is a remote tracking branch and tells us where is the master branch in remote origin) 



Local                   |       remote(repo in github cloud)
                        |                
                        |
master                  |              master 
   |                    |                |
   V                    |                V
   A <-  B              |           A <- B
         ^              |                     
         |              |                        
    orgin/master        |  
                        |


- To make the master in the local repo to point to B as it's supposed to 
- We should merge the <origin/master> with the <master> 
- this will be a <Fast forword merge>     .... 
- supposed it's a <three-way-merge> , we use the merge method suitable for it 
    - If we have conflicts , we should handle them they way it is done ... 
- <git merge origin/master>


> git merge origin/master 

Local                   |       remote(repo in github cloud)
                        |                
                        |
      master            |              master 
         |              |                |
         V              |                V
   A <-  B              |           A <- B
         ^              |                     
         |              |                        
    orgin/master        |  
                        |






# Example in action :         3:28:21 .... 

- create a commit in github directly .... 
# Process ... 
- edit the readme file or do any other change .. 
- git a commit name 
-  Commit directly to the main branch.
- click confirm



# Now we do not  have this new commit in our local repo .... 

# view history 
> git log --oneline --all --graph 
You see that the commit that was just created in the remote repo is not in the local repo .... 

# To download  this latest commit .... 

# To download all commits in that remote repository

> git fetch origin 

# git assumes we are fetching commits from origin

> git fetch

# To download commit(s) from particular branch 

> git fetch origin <branchname>






# we choose .... 

> git fetch 



# View history 
* 8deacee (origin/main, origin/HEAD) New Mars commit
* 6bbd24a (HEAD -> main) Initial commit 

- You see that the remote tracking branch has moved forward ..




# To show how the local branch and remote tracking branch are diverging ..

> git branch -vv





# Now we just need to merge both of them ..... 

> git merge origin/master 
or
> git merge origin/main 










# summary .... 
- download commit 
> git fetch 

- merge the branch holding this commit with the main(master)
> git merge origin/main






# let's check the content of the Readme file to see if what we just did worked ....