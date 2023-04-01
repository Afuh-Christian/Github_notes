# How to commit the snapshots to permanently store in the git repository .... 

> git commit -m "Initial commit" 

NB : -m = message 

# ..if you have a long message to display if you are working with a team 

> git commit 

You will type your message in the given file



# COMMITTING BEST PRACTICES 
- Commit should not be too big or too small
    - We should not use a commit everytime we update a file (it's useless)
    - We should make a commit too big before commiting eg codding for 3 days and then commiting 
- Each commit should represent a logically chain set concept ( don't mix things up)
    - eg if you are fixing a bug and accidentally find a typo in your app  , You shouldn't commit both changes in one commit , 
        - You should have 2 separate commits 
            - one or "typo"
            - another for "bugfix"
        if you accidently stage both changes  , you can easily unstage them ... 

