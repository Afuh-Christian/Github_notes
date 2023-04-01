# 13 Collaboration Workflow       3:46:31      .....   

- I an Amy working on a feature together ...
- One of us should create a <feature branch> and <push> to github 
- We have to create  a remote branch in github .... 
- the branch created is up to date with main .... 


# run fetch to get this new remote tracking branch .. 

> git fetch 

# check if it was gotten successfully ...

> git branch -r
# output .... 
  origin/HEAD -> origin/main
  origin/feature/change-password
  origin/main



# Now to create the local branch that will be linked to this origin/feature/change-password remote tracking branch .... 

> git switch -C <newbranchname>  origin/<remotetrackingbranchname>
or ... 
> git switch -C featureChange origin/feature/change-password




# to checked if creating the new branch and linking to the created remotebranch workd .... 

> git branch -vv
# output 
* featureChange 84b270c [origin/feature/change-password] Add file1.txt
  main          84b270c [origin/main] Add file1.txt




















# Now create a new folder and open a new terminal to simulate Amy's workflow ........ 


- clone the repo .... 

> git clone  https://github.com/Afuh-Christian/Mars.git

- Enter repository .... 

> cd Mars 

- Amy should also create a private branch and match with the <origin/feature/change-password>

> git switch -C feature/change-password origin/feature/change-password





# As Amy ... make a simple commit and push to github ....


> echo password > file1.txt 
> git commit -am "Update file1 by Amyggg" 
> git push
OR ....since it's the current branch .....  
> git push 


# check on github if we have this new commit .... 






# On my teminal .... 
> git pull 
> git switch main 
> git  merge feature/change-password
# view log ... 
> git push



# delete the feature/change-password and origin/feature/change-password .... in both acccounts ..... 

> git branch -d feature/change-password 


> git push -d origin feature/change-password
or
> git push -d -f origin feature/change-password



# To delete tracking branches that are not on the remote ... 
# this is needed because when you delete this remote tracking branch from Me .... It still appears in Amy ... so we use this command to now delete it in Amy because it's not found in the repo .....
> git  remote prune origin




# check to see if ti was deleted .... 
> git branch -r


 












# If I am Responsible for closing the branch ... I have to pull Amy's changes ........