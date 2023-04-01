# 8 Finding Bugs Using Bisect   1:35:37 

- Finding Bugs in particular commits .... 

# - initialize bisect 

> git bisect start 

- New we are in the middle of the bisect operation ..
# ouput 
status: waiting for both good and bad commits









# CHRISTIAN@CLaptop MINGW64 /e/Saved Files/Courses/GITHUB/GITHUB/1  Creating Snapshots/Moon (master|BISECTING)

# we need to set good and bad commits ...

- let's set the last commit to be bad (master|BISECTING) 

> git bisect bad 

# Now we set the first commit to good 

> git bisect good 55f55e9

# output 
Bisecting: 3 revisions left to test after this (roughly 2 steps)
[0ab0a981330c676519c7873151c23b7c7b3d1602] Add gitignore
# means 
3 revisions =  3 commits left 
Add gitinore ...was'nt present at the time .....

# view all the commits now ..... 
- We are using --all because the head has been detached.(as we bisected )

> git log --oneline --all 

# output ...
# fca0d7a (master, refs/bisect/bad) File ts has been staged
1950f41 Added file1 again
6396b1a Deleted file1.txt
f38f0f0 Removed the bin directory that was accidentally committed
# 0ab0a98 (HEAD) Add gitignore
04e7d86 Remove unused code
3d7addc fix the bug that prevented the users from signing up
892f5af new file created
# 55f55e9 (refs/bisect/good-55f55e9d6302eed0ce8e0783e5ad64af8216e608) Initial commit


# HEAD  is in the middle point 
- Git  checked out this commit (git checkout 0ab0a98)
- So the working directory was restored to this point in time  
- So we can run our app (or use automated test) to see if the issue is still there or not
- If the issue was there 
    - the bug is found somewhere between : 
        - 55f55e9 (refs/bisect/good-55f55e9d6302eed0ce8e0783e5ad64af8216e608) Initial commit
        and
        - 0ab0a98 (HEAD) Add gitignore
    - so we just have to examine this section 

- If the issue was no there  
    - the bug is found somewhere between :
        - 0ab0a98 (HEAD) Add gitignore (one step infront)
        and 
        - fca0d7a (master, refs/bisect/bad) File ts has been staged

        


























# Let's say the bug was in the not in the current HEAD
# Bisecting the upper section more to find the bug ..


# CHRISTIAN@CLaptop MINGW64 /e/Saved Files/Courses/GITHUB/GITHUB/1  Creating Snapshots/Moon ((0ab0a98...)|BISECTING)

- Now we will set the (HEAD) (0ab0a98) to  good

- this means we are evaluating the first section (let's say hypothetically that we ran test on the app an found the  error to be at the current head )


> git bisect good

# view commits 
> git log --oneline --all
# fca0d7a (master, refs/bisect/bad) File ts has been staged
1950f41 Added file1 again
# 6396b1a (HEAD) Deleted file1.txt
f38f0f0 Removed the bin directory that was accidentally committed
# 0ab0a98 (refs/bisect/good-0ab0a981330c676519c7873151c23b7c7b3d1602) Add gitignore


# So we do thesame process ... 
- git checkout 6396b1a     ... which is the current head 
- Now the current version of the app ... 
- we run test on the app 
- if error 
    - error btwn 
        -  0ab0a98 (refs/bisect/good-0ab0a981330c676519c7873151c23b7c7b3d1602) Add gitignore
        and 
        - 6396b1a (HEAD) Deleted file1.txt

- else if no err
    - error btwn
        - 6396b1a (HEAD) Deleted file1.txt(one step infront)
        and 
        - fca0d7a (master, refs/bisect/bad) File ts has been staged













# Let's say the bug was in the current HEAD ... 

# CHRISTIAN@CLaptop MINGW64 /e/Saved Files/Courses/GITHUB/GITHUB/1  Creating Snapshots/Moon ((6396b1a...)|BISECTING)

- set current head = good 

> git bisect good 
# output
Bisecting: 0 revisions left to test after this (roughly 0 steps)


# view  commits to see where the error could be ... 

> git log --oneline --all 

# output 

# fca0d7a (master, refs/bisect/bad) File ts has been staged
1950f41 (HEAD) Added file1 again
# 6396b1a (refs/bisect/good-6396b1aaf9aac47581531b582d54edc82bac39af) Deleted file1.txt


NB 
- In this step , we  had 
    - 0 revisions left
    - 0 steps
    - No need to keep bisecting cuze git has found the bad  commit already .... 


# Now we just need to type " git bisect bad " to now give us the actual bad commit .... no need to 
> git bisect bad

# outputs the bad commit ....

1950f419fa568c37a097eb3e0e62ec6ad032c25e is the first bad commit
commit 1950f419fa568c37a097eb3e0e62ec6ad032c25e
Author: Afuh Christian <afuhchristian10@gmail.com>
Date:   Sat Jan 28 19:27:12 2023 +0100

    Added file1 again

 file1.txt | 3 +++
 1 file changed, 3 insertions(+)
 create mode 100644 file1.txt











# No need for the work below cuz we are at 
 - 0 steps .... 



# Let's say the head is a bad commit ... 

# CHRISTIAN@CLaptop MINGW64 /e/Saved Files/Courses/GITHUB/GITHUB/1  Creating Snapshots/Moon ((1950f41...)|BISECTING)

- set current head to bad 

> git bisect bad




















# When we are  done .... we have to asign the HEAD back to the master branch 

> git bisect reset
















