# Using Visual tools to easily compare files .... 

# In git bash ... we have to tell git that we wish to use vscode as our visual tool 

> git config --global diff.tool vscode 

# we have to tell git how to launch vscode  

> git config --global difftool.vscode.cmd "code --wait --diff $LOCAL $REMOTE"

- (--wait) = tells terminal to wait till your done with vs code .(compared the changes and closed the vscode instance )

- (--diff) = tells terminal we want to use it for comparing files 

- ($LOCAL $REMOTE) = Placeholders for old and new copies of the file 

# Now to check if everything is ok 

> git config --global -e

- we can edit our global config settings in our default editor (vscode) with this command 

- ($LOCAL $REMOTE) are lost ... so add them manually ....

# .gitconfig .....
[filter "lfs"]
	clean = git-lfs clean -- %f
	smudge = git-lfs smudge -- %f
	process = git-lfs filter-process
	required = true
[user]
	name = Afuh Christian
	email = afuhchristian10@gmail.com
[core]
	editor = code --wait
	autocrlf = true
[diff]
	tool = vscode
[difftool "vscode"]
	cmd = "code --wait --diff $LOCAL $REMOTE"
# .gitconfig .....


# Now to launch the visual difftool for comparing files ... 

- (working directory) vs (staging area)  
> git difftool

- (staging area) vs (commit)
> git difftool --staged