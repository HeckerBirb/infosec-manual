# 21, FTP
## Anonymous authentication
Sometimes FTP is configured to allow anonymous users to authenticate and potentially gain read and even write access to the FTP server.

### Example commands
```
$ ftp 10.10.10.10
(authenticate with anonymous:anonymous)
```

### Sample output
```
$ ftp 10.10.10.10
Connected to 10.10.10.10.
220 Microsoft FTP Service
Name (10.10.10.10:root): anonymous
331 Anonymous access allowed, send identity (e-mail name) as password.
Password:
230 User logged in.
Remote system type is Windows_NT.
ftp> dir
200 PORT command successful.
125 Data connection already open; Transfer starting.
01-01-01  01:37PM                 1024 .rnd
01-01-01  01:37PM       <DIR>          inetpub
01-01-01  01:37PM       <DIR>          PerfLogs
01-01-01  01:37PM       <DIR>          Program Files
01-01-01  01:37PM       <DIR>          Program Files (x86)
01-01-01  01:37PM       <DIR>          Users
01-01-01  01:37PM       <DIR>          Windows
226 Transfer complete.
ftp>
```

### Suggested mitigations
Disallow anonymous authentication (and use strong passwords for the remaining users).
