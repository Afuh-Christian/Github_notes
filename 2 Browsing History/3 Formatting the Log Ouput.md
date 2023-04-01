# git-scm.com/docs/git-log


# 3 Formatting the Log Ouput 1:22:43 
- You can change the style of the log ouput of the commits to the one favorable ... 

> git log --pretty=format:"%an committed %h on %cd" 

%an = author name 
%h = Hashed ID 
%cd = Commit date

We can formot this how ever we like .. (%) are for using the dynamic values defined in git already ..

# Let's change the color ... of the whole text

> git log --pretty=format:"%Cgreen%an committed %h on %cd" 

%Cgreen = color of all text is now green ..

# change color only of author to green and reset the rest back to white .... 
> git log --pretty=format:"%Cgreen%an%Creset committed %h on %cd" 

%Creset = color of all text except author name is white (default)



# supported colors 
- green 
- red 
- blue