# Common Checks
## Is the kernel patched?
```
uname -a
```
We can search for exploits with searchsploit.
```
searchsploit linux kernel [version]
```

## Do we have sudo rights?
```
sudo -l
```

## Are there are any uncommon SUID/SGID binaries?
```
find / -perm -u=s -type f 2>/dev/null # SUID
find / -perm -g=s -type f 2>/dev/null # SGID
```

## Can we access other users' home directories?
```
ls -laR /root/
ls -laR /home/
```

## What has the user been doing?
```
cat ~/.bash_history
```

## Are there any cronjobs?
```
crontab -l
ls -la /var/spool/cron
ls -la /etc/cron*
cat /etc/cron*
```

## Which services are running?
```
ps aux
ps -ef
```
Which are ran as root?
```
ps aux | grep root
ps -ef | grep root
```

## Can we read sensitive files?
```
cat /etc/shadow
ls -la /var/mail/
```
