# Some files and directories that are not important have to be ignored .. eg 
- log files 
- node_modules 
- etc 

# Let's create a directory called logs 

> mkdir logs 

- add a file into it 

> echo hello > logs/dev.log

# if we run the git status ... we see and error of logs/ being tracked 
- we do not want git to track this .... 

# to do this ... 
- create a file called ".gitignore"
- it should be in the root of your project 

> echo logs/ > .gitignore 
OR 
> echo *.log > .gitignore    .... all files with .log ... 

- creates .gitignore file and adds logs/ into it ... 
- You can still do this manually 

# check status   
- we now see that we need to add .gitignore to the staging area 
- Git no longer tracks the logs file

> code .gitignore           ... to open .gitignore to vscode 

# add .gitignore to staging area 

> git add .gitignore




# Now we see that git only tracks 
- .gitinore 
- file1.txt

> git commit -m "Add gitignore"























# NB ... If the files you wish to ignore is already in your repository , and you later add gitignore ... git will not ignore it ... 

create a bin directory , add it to the staging files and now try to ignore it ... 

>mkdir bin 
>echo hello > bin/app.bin 
> git add bin 
or 
> git add . 

# bin is now part of the staging files .... 
# Now add it to .gitignore 

> echo bin/ >> .gitignore

> git add . 
> git commit -m "Include bin/ in gitignore."

# this will not ignore bin/ because git is already tracking changes in the bin directory .... and also if you check the files in the staging area with the command "git ls-files" ... you see that bin is still there .... 
- if we modify our bin files and check status ...we get an error ... meaning git is still tracking it's changes .... 
- but logs updates are not visible to git ... 

# Now we need a git command that removes a file only from the staging area ... 
> git rm bin ... will remove git from staging area and working directory and we do not want that .... 

# we can check by typing 
> git rm -h              ... to check other command with rm ...
  
  --cached   :  only remove from the index(staging area)
  -r    : allow recursive removal 
# So the command to remove a file or forlder from staging area (index) will be ... 

> git rm -r --cached bin/



# git status .... 
- we have one change ready to be committed .. 

> git commit -m "Removed the bin dir that was accidentally commited"



# done ... we can verify "git ls-files" ... 
# Now git , no longer tracks changes in the bin .... 
