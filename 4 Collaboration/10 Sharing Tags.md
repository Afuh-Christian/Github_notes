# 10 Sharing Tags         3:39:12           ...... 

- By default the <push> command does not transfer our tags to the <remote repo>  .... 

- we have to <explicitly push the tags >




# Example ...  
- create a new tag ... 
- it'll be added to the last commit automatically .. view logs to verify ... 


> git tag v1.0 
> git push origin v1.0


<Done>  .. 

When you check the repo ... 
- there an area for tags 
- You can view all tags ... 
- You can download a zip of the project in that tag(commit)



# How to remove a tag from the <remote repo> ... if it was put there by accident ... 

> git push origin --delete v1.0


# but the tag is still in the <local repo>  ....view logs to see
# remove from <local repo> 

> git tag -d v1.0