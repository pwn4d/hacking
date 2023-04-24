Ip = 10.10.132.108






![[Pasted image 20220605130737.png]]


I started with a quick nmap and dirbsuter scan

![[Pasted image 20220605130807.png]]


## Directories and Files[
	.hta
	.htaccess
	.htpasswd
	css
	index.php
	js
	panel
	server-status
	uploads
	
]


I found quite a few interesting files to have a look at

## /panel


![[Pasted image 20220605131040.png]]

Appears to be some kind of file upload possibly leading to remote code execution



## /uploads


	![[Pasted image 20220605131146.png]]

I was able to access the contents of /uploads


Lets try uploading a php reverse shell to the website



## Creating php reverse shell

![[Pasted image 20220605131408.png]]

Creating a php reverse shell with msfvenom




![[Pasted image 20220605131550.png]]

It seems php is not allowed 



## File Upload Bypassing

By changing shell.php -> shell.phtml I was able to bypass the server side file upload filters


From here I went to uploads/shell.phtml and it executed and gave me a session

![[Pasted image 20220605134036.png]]



## Post exploitation


I very quickly found a user.txt ion the `/var/ww` directory

![[Pasted image 20220605134322.png]]



I found that the binary `/usr/bin/python` had a SUID bit 

I found a very handy guide on https://gtfobins.github.io/gtfobins/python/ and was easily able to get root 


## `python -c 'import os; os.execl("/bin/sh", "sh", "-p")'



![[Pasted image 20220605144328.png]]


