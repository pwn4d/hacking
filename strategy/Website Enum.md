# Fuzz Directories [`feroxbuster`]



 ## feroxbuster --url http://10.10.107.89 -w ~/stuff/tools/SecLists/Discovery/Web-Content/directory-list-2.3-medium.txt

(Default wordlist is `/usr/share/seclists/Discovery/Web-Content/raft-medium-directories.txt` but I just rename `directory-list-lowercase-2.3-medium.txt` to make things easier )


# Fuzz subdomains

## gobuster vhost -u http://example.com -w ~/stuff/tools/SecLists/Discovery/DNS/subdomains-top1million-110000.txt
-w: specify wordlist
-u: domain to attack
-H: specify which part of domain to attack
-fw: useful if flooded with false positives


# Checking Default Favicon.ico [Webpage Software & Version]

Get Md5 hash of favicon.ico

## `curl <url>.favicon.ico |md5`

![[Pasted image 20220604230524.png]]

![[Pasted image 20220604230638.png]]

Here we see the server is running  `cgiirc`  on versino `0.5.9`


# Check HTTP headers

## `curl <url> -v`

![[Pasted image 20220604231304.png]]







# nikto

## `nikto -h`

- -h : specifies host e.g https://google.com