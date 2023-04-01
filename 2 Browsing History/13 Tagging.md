# 13 Tagging   1:45:00

- Quite often , we have to bookmark certain points in  the history of our project
    - like the commit that represent's a given version


# To tag the latest commit 

> git tag <versionname>
e.g 
> git tag v1.5

# Tag a particular project with a version 

> git tag <versionname> <commitID>
e.g
> git tag v1.0  55f55e9


# View the logs .... 
8019df1 (HEAD -> master) File2.txt Restored in working directory
bcc5d8f Removed file2.txt
fca0d7a File ts has been staged
1950f41 Added file1 again
6396b1a Deleted file1.txt
f38f0f0 Removed the bin directory that was accidentally committed
0ab0a98 Add gitignore
04e7d86 Remove unused code
3d7addc fix the bug that prevented the users from signing up
892f5af new file created
# 55f55e9 (tag: v1.0) Initial commit

# we can reference that commit using the versionname .. 

- this command will revert the project directory to 
that point in time .... 

> git checkout v1.0  



# to see all the tags you have created 

> git tag

# ouput
v1.0


# the types of tags we have been using is called a "light weight tag" 
# Light weight tag

- it's just a reference(pointer) to a particular commit 
- how to create a light weight tag 

> git tag <versionname> <commitID>


# Anotated tag 
- a complete object with a bunch of properties 
- to create annotated tag 

> git tag -a <versionname> -m "My version 1.1"

-a = annotated
-m = message like in a commit (a custom message)

# example 

> git tag -a v1.1 -m "My version 1.1"






# Now view all tags 

> git tag 

# view all tags plus their messages 

> git tag -n 
# output 
v1.0            Initial commit
v1.1            My first version 1.1



# NB ...
 - Light weight tag v1.0  => it's message = commit message 
 - Annotated tag v1.1 => it's message = custom message 





# Now to view the files of one of the tags .... 

> git show v1.1

- the ouput gives info about the tagger and and the commit .... 
- this is why we prefer "ANNOTATED TAGS" 


















# To delete a tag ..... 

> git tag -d <tagname or versionname> 

e.g  

> git tag -d v1.1