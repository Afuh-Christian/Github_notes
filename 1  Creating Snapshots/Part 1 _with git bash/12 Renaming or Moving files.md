# RENAMING FILES IN DIRECTOR AND STAGING AREA 
- let's rename "file1.txt" to "main.js"

# Method 1 ...........................
> mv file1.txt main.js

# check status  
we see that we have to stage the deletion and stage the addition of the new file ... 

> git add file1.txt        ... deletion 
> git add main.js          ... addition


#  Method 2 .........................

> git mv file1.txt main.js

# After any of the methods .... check the staging area to see the files 
> git ls-files 



# then commit the change ... 
> git commit -m "Filename changed"


# the stats of the message 

0 insertions = we haven't any new lines in the file 
0 deletions = we haven't deleted any lines in the file 















# Mayble 

> git mv main.js file1.txt