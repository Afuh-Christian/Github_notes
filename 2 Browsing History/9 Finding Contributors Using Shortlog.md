# 9 Finding Contributors Using Shortlog ...... 1:40:05

- How to find all the people who have contributed to our project 
- the shorlog command displays the Username , number of commits he/she has created and a list of all those commits ..

> git shortlog 

# output 
Afuh Christian (9):
      Initial commit
      new file created
      fix the bug that prevented the users from signing up
      Remove unused code
      Add gitignore
      Removed the bin directory that was accidentally committed
      Deleted file1.txt
      Added file1 again
      File ts has been staged



# to check for help to see the  other options shorlog has ... 

> git shortlog -h

# we can view the contributors for a given date range ... 

> git shortlog --before=""
> git shortlog --after=""





