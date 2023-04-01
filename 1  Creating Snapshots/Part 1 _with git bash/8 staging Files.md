# 00:21:46
# EXAMPLE 
- Add a couple of files to the project .... 

- create a .txt file with "hello" in it .
> echo hello > file1.txt 
> echo world > file2.txt 

# to see status of working directory and staging area 
> git status

# add files to staging area 

> git add file1.txt file2.txt      .. add specific files 
OR 
> git add *.txt          .. all files with .txt
OR 
> git add .              .. Entire directory 

# run git staus to check changes 

> git status

# to remove files from staging area 

>git rm  --cached <file>..." to unstage

# Update the text in file1 ... append world to hello in file1 

> echo world >> file1.txt

# run git status and you'll get a complain about the modified file in the working directory ... 

# Now we need to add the newly edited file1.txt to the staging area alone and the check the status , we surely wouldn't get the error again 

> git add file1.txt 
> git status 






# check staged and unstaged files , which are not committed 
> git status -s
or
> git status 


# check files in staging area  
> git ls-files


# unstade files / remove files     ..... from staging area
>git rm  --cached <file>







