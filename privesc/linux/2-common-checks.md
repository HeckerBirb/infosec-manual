# Common Checks
## Can we access other users' home directories?
What sensitive information can we find in the different user directories?
```
$ ls -laR /root/
$ ls -laR /home/
```

## Cronjobs
Are there any cronjobs of particular interest?
```
crontab -l
$ ls -la /var/spool/cron
$ ls -la /etc/cron*
$ cat /etc/cron*
```

## Running services
Are any programs of interest running? Interesting candidates are programs that look out of the ordinary and run as `root` or other user accounts of interest.
Not that the `-f` flag can be left out depending on preference. This gives a tree-like structure of the processes running and shows child processes in relation to their parrent processes.
```
$ ps -auxf
$ ps -ef
```
This can be combined with `grep` for easier reading:
```
$ ps -aux | grep root
$ ps -ef | grep root
```

## Local mail
Is any interesting or sensitive information found inside the user mail? Can we read it?
```
$ ls -la /var/mail/
```
