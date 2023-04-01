# run all you're commands on gitbash to prevent complications 

# Create directory for project
> mkdir <foldername>

> mkdir Moon
> cd Moon

# initialize a new empty repository for the files you  wish to upload 
> git init
- result
Initialized empty Git repository in E:/Saved Files/Courses/GITHUB/Notes/Moon/.git/
- .git is hidden by defualt 
- .git is not suppose to be edited by user

# list all files in directory 
> ls
- we see nothing 

- To show encrypted content
> ls -a              .... a = all 
- ./  ../  .git/

# To open this directory 
> start .git

# You see the file structure 
- hooks
- info
- objects
- refs 
- config
- description
- HEAD

# NB 
- this is where git stores info about project history 
- We need to understand just how it stores the info ... 
- We don't need to understand the structure 


# Do not delete this .git ... else you'll loose your project history

to remove file/folder
>rm -rf .git



# Now that we have the repository ,  we will tald about the basic git workflow ...




# To go back on git bash 

cd .. 