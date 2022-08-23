### git process  

ssh key stuff:  
ey generations notes
---------------------
sudo ssh-keygen
Generating public/private rsa key pair.
The key's randomart image is:
+---[RSA 3072]----+
|    . . o..o.    |
...
|.  . ==o++       |
|    o=XB.        |
+----[SHA256]-----+

==========================


> public key in vi:
---------------------   
- vi id_rsa.pub


copy key ~ starts with ssh-rsa ...
past as new key for the github repo






use git to clone:  
----------------  
 sudo git clone https://github.com/<x>/<x>.git  

git push:  
--------  
$ sudo git add cvx   <-- add file  
$ sudo git status    <-- verify added and ready for commit  
$ sudo git commit    <-- commit -m "info about commit"  
 
$ sudo git push origin --all
Username for 'https://github.com': <x>
Password for 'https://<x>@github.com': <token>
