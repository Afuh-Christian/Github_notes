# 12 Sharing Branches           3:43:10           

- So far we have been doing all the work on master .... 

- Let's work with branches ..
- Similar to tags , Our branches are private or local by default
- So to collaborate with team members using a branch , we have to explicitly <push the branch> thesame way we push tags 





# Example .... 

- create new  branch and switch to it ... 
> git switch -C feature/change-password

- Now try to push the branch ... 
> git push 
# outupt 
fatal: The current branch feature/change-password has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin feature/change-password

# To have this happen automatically for branches without a tracking
upstream, <see 'push.autoSetupRemote' in 'git help config'.



# Nb .. the above error means that the branch we are trying to push is not linked to any branch in origin ..... 

# let's check the branches and their links ... 

> git branch -vv 
# output
* feature/change-password 84b270c Add file1.txt
  main                    84b270c [origin/main] Add file1.txt



- From above , main(master) is linked to [origin/main] while 
<feature/change-password> is currently linked to nothing in the remote repo


# To see all the remote tracking branches 

> git branch -r
# output
  origin/HEAD -> origin/main
  origin/main




















# To link this private branch to a branch in origin .... 

> git push --set-upstream origin feature/change-password 
Or 
> git push -u origin feature/change-password


<Done> 


we can  verify on github ..... 





# Or we can check the branches that are linked 

> git branch -vv 
# output
* feature/change-password 84b270c [origin/feature/change-password] Add file1.txt
  main                    84b270c [origin/main] Add file1.txt



# Or we  can check the available remote tracking branches .. 

> git branch -r 
# output
  origin/HEAD -> origin/main
  origin/feature/change-password
  origin/main





<Now we see that the feature/change-password now has a remote tracking branch ...>








# How to delete the remote branch ... after using it ... 

> git push -d origin feature/change-password





# check to see if ti was deleted .... 
> git branch -r 
or 
> git branch -vv 
or 
https://github.com/Afuh-Christian/Mars














































