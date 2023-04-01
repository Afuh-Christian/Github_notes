# if we wish to undo the changes we did in the staging area that should not be commited

# we need to undo the "git add "  .... files ready to commit ..
> git restore --staged file1.txt

- what happens is that git takes the last copy of this file in the commit and replaces it in the staging area .. so that file1.txt will no longer be ready to commit because they are thesame now ....  

















# files waiting to be  added to staging area  ... restoring the old version of the files in the working directory ...
> git restore file1.txt  

- will restore a the file1 in the working directory .... by taking it's copy in the staging area and placing in the working directory .... 


# To remove all untracked files from the staging area .... 

> git clean -h
> git clean -fd