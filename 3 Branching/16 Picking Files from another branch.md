# 16 Picking Files from another branch   2:59:52 

- Picking up just files and not whole commits from a single branch to another branch .... 


- create a new branch to test this out ... 
# featureC
> git switch -C featureC  
> git river > demo.txt
> git commit -am "featureC filepicK"


# master 
> git switch master 
> git river > file1.txt
> git commit -am "featureC filepicK"

# View history 
> git log --oneline --all --graph
* 3e1fdb9 (HEAD -> master) featurec file pick master
| * 09acbf0 (featureC) featurec file pick
|/
* 6c13d55 Update demo m feature update in master



# - we wish to bring this demo.txt from the featureC to the master branch .... 

> git restore --source=<targetbranch> -- <filename>
e.g 
> git restore --source=featureC demo.txt 



> git status -s 
M demo.txt


# Nb ... we can view contents of a file using 
> cat <filename>
e.g 
> cat demo.txt







# Now we can stage and commit this change in the master branch .... 

> git commit -am "update master Picking ..."




