# How to skip the staging area .. 
- You do not always have to stage you're changes before committing them .. 
- Do this if your 100% sure about your code 

# let's edit a file1.txt and commit  it 

> echo test >> file1.txt

> git commit -a -m "updated" 
> git commit -am "updated" 

NB : -a = all updated files , -m = message

# NB ... this only works when you are editing a file 