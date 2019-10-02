# Quick Wins
## Kernel exploits
An outdated kernel is often vulnerable to kernel-level exploits, typically to escalata priveleges from a low priveleged user account to the `root` user.
```bash
$ uname -a
```
One can use the `searchsploit` command (a command line alternative to the Exploit-DB) to search for kernel exploits:
```bash
$ searchsploit linux kernel [version]
```

## Sudo permissions
Low privileged users which are permitted to run some or all programs as `root` through `sudo` pose a risk if not handled correctly or if the password is known. To check the sudo permissions, use the below command.
```bash
$ sudo -l
```

## Uncommon SUID/SGID binaries
Sometimes one may be so lucky as to find a program or shell script that has SUID or SGID set to run as `root` or other high privileged user. Find all such files like this:
```bash
$ find / -perm -u=s -type f 2>/dev/null # SUID
$ find / -perm -g=s -type f 2>/dev/null # SGID
```

## Read or write permissions to sensitive files
Can we edit the `/etc/passwd` file and, for example, change the UID of our low priv user to 0 (`root`)? Can we update or read the `/etc/shadow` file?
```bash
$ ls -l /etc/passwd
$ ls -l /etc/shadow
$ ls -l /etc/group
```

## Credentials in history
Are passwords or other interesting commands stored in the history from earlier usage?
```bash
$ cat ~/.bash_history
$ cat ~/.mysql_history
$ cat ~/.php_history
```
