# 10 Viewing the history of a file ...

- Find all the commits that have touched a particular file ... 

> git log  file1.txt
or
> git log --oneline file1.txt

- Check the stats on each commit on that file , what happened ... 

> git log --oneline --stat file1.txt

- To see the actual changes in each commit ... 

> git log --oneline --patch file1.txt