# Creating aliases 1:26:08 

How to create aliases for long command that we can't remember and we use frequently so we do not have to type it all everytime ..


- we will set an alias globally that will represent a particular format  .... 
- alias.lg   : lg is the new property created 
- with value in ""


> git config --global alias.lg "log --pretty=format:'%Cgreen%an%Creset committed %h on %cd'"

# we check the gitconfig if the new property lg is being created .. 

> git config --global -e

# Now  to use the style with the use of the alias we set  ..... We have just created a custom log format ...

> git lg


















# We can create anytype of alias we want ...... an they are set globally so we will be able to use them on any repository so long as I'm the user logged in to this computer ...  

We just created a short method to unstage all staged files ... 

> git config --global alias.unstage "restore --staged ." 

> git unstage


