# 10 Visual Merge Tools    ....  2:33:01 

- kdiff 
- P4Merge
- winMerge(windows only)


# we will use P4Merge form resolving confilts 

# Install P4Merge

https://www.perforce.com/products/helix-core-apps/merge-diff-tool-p4merge

- click download



# How to configure P4Merge to the bit bash ..... 

> git config --global merge.tool p4merge

- we tell git where to find p4merge

> git config --global mergetool.p4merge.path "<fullpathto-p4merge"
e.g 
> git config --global mergetool.p4merge.path "C:\Program Files\Perforce\p4merge.exe"






# Now we need to test this out with an existing conflict .... .. 

create a merge conflict scenario and test it out with the p4merge .. 
- create a new branch 
- do an edit in one file in that branch 
- do another edit in that same file , now on the master branch .... 

> git switch -C ptestbranch
> echo  ptestbranch change >> demo2.txt
> git add . 
> git commit  -m "p4test" 

> git switch master 
> echo master change >> demo2.txt 
> git add . 
> git commit  -m "p4test" 




# To merge with the tool we added ... .2:35:57

> git mergetool

# NB  ... the will not work if the edit we are doing concerns adding another file ... else we'll have to use the old fashion method .... 

- this method  will work if we are editing an existiong file .... 

# Now in the visual tool ... 

- we save the changes , 
- close it ... 
- go back to terminal 
- add and commit the changes ..
> git add . 
> git commit 

Now it has been merged ... 

