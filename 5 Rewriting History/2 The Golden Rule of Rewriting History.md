# 2 The Golden Rule of Rewriting History 4:27:03 ...

# - 1 - Don't Rewrite public history ...............................................................................................................................................................................................................................................................

- If you have pushed you're commits to share your work with others , <those commits are considerd public> and we shouldn't modify that ...

- <explanation>
- commits in git are <immuatble>

local                      |                            remote
                           |
   master                  |                     master
     |                     |                       |
A <- B                     |                  A <- B
     |                     |
origin/master              |

- once you try to modify a commit <B>, git will create new commit <B\*> ..
  <B> will stay in git's database incase you wish to recover it.

local                      |                            remote
                    <git push  .. rejected>
   master                  |                     master
     |                     |                       |
A <- B                     |                  A <- B
  \                        |
   \                       |
    B*                     |
origin/master              |


- Let's try to <push the changes> to the <public remote repo>
- Git will <reject our push>

- <Resolving the push reject.... >
- First we have to <merge B\* and B intor master> then we push...


local                      |                            remote
        <git merge>        |
   master                  |                     master
     |                     |                       |
A <- B <- M                |                  A <- B
  \   ___/                 |
   \ /                     |
    B*                     |
origin/master              |


- Now we <try pushing again> ...

local                      |                            remote
                       <git push>
   master                  |                     master
     |                     |                       |
A <- B <- M                |                  A <- B <- M
  \   ___/                 |                   \   ____/
   \ /                     |                    \ /
    B*                     |                     B*
origin/master              |



- Now the <local and remote repo have thesame history>

# Drawback ....
- we have created and nonlinear noisy history , <B> and <M> are unneccessary ...
- We were just trying to modify <B> , so why should we keep it in history and share with others ...



# An Alternative solution ...............................


local                      |                            remote
                           |
   master                  |                     master
     |                     |                       |
A <- B                     |                  A <- B
  \                        |
   \                       |
    B*                     |
origin/master              |

- So we use <git push -force> : this will overwrite the commits we have  in origin(remote)
    - Now in origin ... git will Drop <B> and replace with <B*>
    - An then in the local repo , git will attarch <origin/master> and <master> to <B*> 
    
local                      |                            remote
                  <git push -force>
   master                  |                     master
     |                     |                       |
A <- <B*>                  |                  A <- <B*>
     |                     |
origin/master              |


# - This options looks greate ,,, but it's not .... 
Reason ... 
- Let's say there's another person working on this public repo say john ..
- John knows nothing about the change that occured in the orgin 
- He makes a commit on the project he cloned and tries to <push> , it will be <rejected>


<John>                     |                            remote
                  <git push .. rejected>
   master                  |                     master
     |                     |                       |
A <- B <- C                |                  A <- <B*>
          |                |
      origin/master        |


- He will have <pull> , then <merge> and then <push> ... 


<John>                     |                            remote
                           |
    master                 |                      master
      |                    |                        |
 A <- B <- C <- M          |                  A <- <B*>
  \     _______/           |
   \   /                   | 
    <B*>                   |  
      |                    |
  origin/master            |


- Once again we have created a <noisy non linear history> <C> , <M>   <B>



# So remember the Golden rule  "DON'T REWRITE PUBLIC HISTORY"


# It's very safe to rewrite private history since no one else get's affected .... 

