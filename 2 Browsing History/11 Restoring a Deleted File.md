# 11 Restoring a Deleted File ...... 1:42:32

- You may accidently delete a file from the working directory 
- How to recover the file from the history 

# let's remove a file from the working director / staging area  and replace it back .... 


> git rm file2.txt 
> git commit -m "Removed file2.txt"

# Now  we find all the commits associated to this file  
(--)  since file2.txt is untracable from the working directory
> git log --oneline -- file2.txt


# output 
bcc5d8f (HEAD -> master) Removed file2.txt
6396b1a Deleted file1.txt
04e7d86 Remove unused code
55f55e9 Initial commit

# obviously , the last commit (bcc5d8f) deleted this file ... so  we choose another commit closer to the  last (6396b1a)

- checkout a file in a  particulart commit 
- update the directory with just that file .....

> git checkout 6396b1a file2.txt

# - Now we have an file2.txt in the working direcory and in the staging area ready to be committed


> git commit -m "Restored file2.txt"