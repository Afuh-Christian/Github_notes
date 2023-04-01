#  viewing the staged & unstaged changes

# We need to review the code  before committing .... 
# status only checks file updates,delete and addition ... but does not know about the code .... 


# So this command will be used to check what we have in the staging area ... 


# - this compares the version of files found the the latest commit and that of the staging area which have not been committed   ..  .. 00:47:00
- commit 
- staging area ...

> git diff --staged

# output .......(prefix (-)  = deleted content).........(prefix (+ = added content))...........
diff --git a/file1.txt b/file1.txt
index 4ffc873..06cb937 100644
--- a/file1.txt
+++ b/file1.txt
@@ -1,3 +1,4 @@
 hello , file2.txt
 world
 test
+new
diff --git a/file2.txt b/file2.txt
new file mode 100644
index 0000000..ce01362
--- /dev/null
+++ b/file2.txt
@@ -0,0 +1 @@
+hello
# output .............

l1 - comparing copies of thesame file 
l2 - some metadata
l3 - Changes in old copy represented by ----
l4 - Changes in new copy represented by ++++
l5 - Header with info about what parts of the file is changed 
    - if you update a small portion of the file git will not show the whole file but show that small part as a "chunk"
        - Every chunk has a header 
    - Header = ( @@ -1,3 +1,4 @@  )
        - segment 1 (@@ -1,3)  = infor about old copy 
            - starting from line 1 , 3 lines have been extracted and shown 
        - segment 2 (+1,4 @@)  = infor about new copy 
            - starting from line 1 , 4 lines have been extracted and shown 
            - You see that +new , is prefixed with a + ... 
                - it's new data added in the new copy

# the next set ... 
--- /dev/null          ... this is because theres  old copy in the commit 
+++ b/file2.txt



















# - compares the version of files in the staging area and working diretory ...... 
- staging area 
- working directory  ...

NB ... if you have already added the updated files to the staging area ... nothing will be displayed in the git diff result because all the old and new copies will be thesame ... 


- make a change to file1.txt ... the run git diff ... 

> git diff 

# Output ...........
diff --git a/file1.txt b/file1.txt
index 06cb937..dffb9b9 100644
--- a/file1.txt
+++ b/file1.txt
@@ -2,3 +2,4 @@ hello , file2.txt
 world
 test
 new
+hobbu
# Output ..........

