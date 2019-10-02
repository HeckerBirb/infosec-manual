# Common Checks
## Are there any services only available internally?
```powershell
netstat -ano
```

## Which privileges do we have?
```powershell
whoami /priv
```

## What users are on the machine?
```powershell
net users
```

## Which processes are running?
```powershell
tasklist /v
```
Which are ran as system?
```powershell
tasklist /v /fi "username eq system"
```

## Are there any scheduled tasks?
```powershell
schtasks /query /fo LIST
```

## Are there any unquoted service paths?
```powershell
wmic service get name,displayname,pathname,startmode |findstr /i "Auto" |findstr /i /v "C:\Windows\\" |findstr /i /v """

gwmi -class Win32_Service -Property Name, DisplayName, PathName, StartMode | Where {$_.StartMode -eq "Auto" -and $_.PathName -notlike "C:\Windows*" -and $_.PathName -notlike '"*'} | select PathName,DisplayName,Name
```

