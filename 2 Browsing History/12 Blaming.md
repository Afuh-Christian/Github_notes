# 12 Blaming .....   
- With this you can find the author of a particular line 
- As part of troubleshooting issues , we can use this this to investigate who wrote the line of code that caused the error


# Find the author who created a particular file and made changes in it , or authors who have something to do with a particular file .... 

> git blame file1.txt

# output 
1950f419 (Afuh Christian 2023-01-28 19:27:12 +0100 1) hello , file2.txt
1950f419 (Afuh Christian 2023-01-28 19:27:12 +0100 2) world
1950f419 (Afuh Christian 2023-01-28 19:27:12 +0100 3) test
fca0d7ae (Afuh Christian 2023-01-29 12:41:30 +0100 4) myhousekkk


# To get the author's email

> git blame -e file1.txt

# To get just the first 3 commit's(lines of edits) 

>  git blame -L 1,3 file1.txt

# output
1950f419 (Afuh Christian 2023-01-28 19:27:12 +0100 1) hello , file2.txt
1950f419 (Afuh Christian 2023-01-28 19:27:12 +0100 2) world
1950f419 (Afuh Christian 2023-01-28 19:27:12 +0100 3) test
