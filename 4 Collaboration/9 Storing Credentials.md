# 9 Storing Credentials   3:37:27      ...


- When I try to <push> my commits , I have to enter my github credentials 
- we can store our credentials in memory , and tell git where to  find it 

- we need to set a config value

# Set to cache : git will store for 15 minutes in memory 

> git config --global credential.helper cache


# Set to cache : to store indefinitely 
- mac: keychaing 
- windows: Windows Credential Store 
These are both storages for storing sensitive data
So the credentials will be stored in an <encrypted-way>

# proces .... 

- 1 install  Git-Credential-Manager-for-Windows from .............. https://github.com/microsoft/Git-Credential-Manager-for-Windows

- download from ....
https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/tag/1.20.0










