# 2 Filtering History .......  1:17:49

- This repository has just a few commits ... 
- Repositories in the real world usually have hundreds of commits , 
- we can't go through all thouse commits .. 
- so we have to filter by 
    - auther 
    - date 
    - commit message
    - content 
    - Id  , etc 

#  To see the last 3 commits ... 

> git log --oneline -3 

# Filter by author ..............................

> git log --oneline --author="Afuh"


# Filter by Date ..............................

# i ....  after this date 
> git log --oneline --after="2023-01-27"
> git log --oneline --after="yesterday"
> git log --oneline --after="today"
> git log --oneline --after="one week ago"
> git log --oneline --after="one month ago"

# i .... on this date and before 
> git log --oneline --before="2023-01-27"


# Filter by word present in message ... ............case sensitive..................

> git log --oneline --grep="Add"


# Filter by content ... the commit that was responsible for altering a particuler part of the content ...... ...........................
- the commit that added "world" 

> git log --oneline -S"world"

# we can use the --patch  to see the actual changes in this particular commit (or list of commits ..)

> git log --oneline -S"world" --patch




# Filter by "RANGE OF COMMITS" 
NB - this is in the reverse order .. so the older commits are down while the new are up ....

display commits from 3d7addc to 6396b1a

 > git log --oneline 3d7addc..6396b1a



# Filter by all commits that touch a particular file or a bunch of files .... 
find all commits that have modified file1.txt

> git log --oneline file1.txt

   # Nb ... do it like this more often cause you'll meet files that are not compatible and you'll get errors
   # the (--) separate the filename from the (--oneline) options we are useing ..
> git log --oneline -- file1.

  # To see the actual changes in each of these commits , we use the patch options ... 
  # NB .... the (--patch) must come before the filename 
  # this is because after the empty(--) git interprets everything after it as a filename

> git log --oneline --patch -- file1.txt






