# Quick Wins
## Kernel exploits
```bash
uname -a
```
Search for kernel exploits
```bash
searchsploit linux kernel [version]
```

## Sudo permissions
```bash
sudo -l
```

## Uncommon SUID/SGID binaries
```bash
find / -perm -u=s -type f 2>/dev/null # SUID
find / -perm -g=s -type f 2>/dev/null # SGID
```

## Read or write permissions to sensitive files
```bash
ls -l /etc/passwd
ls -l /etc/shadow
ls -l /etc/group
```

## Credentials in history
```bash
cat ~/.bash_history
cat ~/.mysql_history
cat ~/.php_history
```
