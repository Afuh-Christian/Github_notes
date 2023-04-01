# 12 How to squash a few commits together   5:01:29  ..... 

<we are trying to join two or more commits whose changes are related > 

<View log> 
* 9ac468f (HEAD -> master) 3nd
* 48544a3 2nd
* 6adc870 1st
* 59f042a added 2 to File2
* 44bbe49 added 1 to f2
* 0df7271 Initial C



# Let's say we want to combine ... 3nd and 2nd into 1st ... 

> git rebase -i 6adc870~1

- We change the options to ... 
 <squash> 2nd
 <squash> 3nd

- choose a new commit message 

<View log ...> 
* 32d7c95 (HEAD -> master) 1st 2nd 3nd
* 59f042a added 2 to File2
* 44bbe49 added 1 to f2
* 0df7271 Initial C






























# How to use the <r fixup> option in <rebase -i>  ... 5:03:00

- Fixup is liked <squash> .... but here the message we are combining into is the default message ... we are not be asked to provide a message 
