# 9 Dropping a commit   4:54:00             

# Droping an earlier commit .... 

<view log> 
* dad0706 (HEAD -> master) Edited map
* 3200213 Render cafes on the map. to use
* fc8a0d3 Revert numbers file
* 17dd265 added 2 to f2
* 0c3cacc added 1 to f2
* 1cf679f Created f2
* 0df7271 Initial C


# Let's drop ....  1cf679f Created f2

> git rebase -i 0df7271 
or
> git rebase -i 1cf679f~1
or 
> git rebase -i 1cf679f^ 

# 
> git status -s 
there is a conflict because of a presence of a file that was removed as an earlier commit removed ....
# output 
A  c.txt
DU f2.txt

<DU we are trying  to delete and update the file..>
<this changes  will go with the next commit ...>

# resolve conflict ... 
> git mergetool

we will choose the modification(m) .... 

> git status -s 
A  c.txt
A  f2.txt


# We have two files ready to be committed ... 

- we continue with the rebase operation ..... 

> git rebase --continue

NB... do not allter the commit name ..



# Now view the log and you find one commit deleted .... 























# Let's try dropping the last 3 commits 

> git rebase -i HEAD~3 

- change the option of the 3 commits above to be <drop> 
- exit the file ... 


# there was no conflict here ... 

<View log> 
* 8a0f6f8 (HEAD -> master) added 2 to f2
* 44bbe49 added 1 to f2
* 0df7271 Initial C


